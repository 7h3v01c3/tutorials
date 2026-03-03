# Divi Regnet Setup for Developers

Walkthrough for running one or more Divi nodes in regnet on a single machine. Use this for integration development, RPC experiments, or ZMQ testing without touching mainnet or testnet.

## Prerequisites

- Divi Core (`divid`, `divi-cli`) installed
- Separate data directories for each node (so they do not share chain or wallet)

## Directory layout

Under your Divi data path, create `regnet` and one or more **node roots**: `node1`, `node2`, `node3`. Each node root contains two things:

1. **divi.conf** – config file in the node root.
2. **data** – directory for blockchain and wallet files. You must create this and point the daemon at it.

Example for one node:

```
REGNET/
  node1/
    divi.conf      ← config
    data/          ← blockchain + wallet (use -datadir=.../node1/data)
```

| OS      | Node root (create these) | Data directory (use with -datadir) |
|---------|---------------------------|-------------------------------------|
| Windows | `%APPDATA%\DIVI\REGNET\node1` | `%APPDATA%\DIVI\REGNET\node1\data` |
| macOS   | `~/Library/Application Support/DIVI/REGNET/node1` | `~/Library/Application Support/DIVI/REGNET/node1/data` |
| Linux   | `~/.divi/REGNET/node1` | `~/.divi/REGNET/node1/data` |

Create the **data** directory inside each node root (e.g. `node1/data`). Start `divid` and `divi-cli` with **-datadir** set to that data directory so chain and wallet files go there. Put **divi.conf** in the node root (e.g. `node1/divi.conf`). If your build only reads config from the datadir, put divi.conf inside `node1/data/` instead.

Create only the nodes you need. For node2/node3 use the same layout (node2/divi.conf, node2/data; node3/divi.conf, node3/data) and unique `port` and `rpcport` in each config.

### Config and peers in divi.conf

Put options (including peers) in **divi.conf** in each node root. Use a unique `port` (P2P) and `rpcport` per node, and `addnode=127.0.0.1:<other node port>`. If every node lists the others, they are fully connected.

See **divi.conf.REGNET.example** in this folder. Copy it to your node root (e.g. `node1/divi.conf`). For node2 use `port=51476`, `rpcport=61476`, and addnode for 51475 and 51477. For node3 use `port=51477`, `rpcport=61477`, and addnode for 51475 and 51476.

---

## One-node setup

Single node: good for RPC, ZMQ, or address/wallet experiments.

If you use **divi.conf** in the node root, create the node root and its **data** directory, copy the example as `node1/divi.conf`, then start with `-datadir=<path-to-node1/data>`.

1. **Start the node** (use the **data** directory for `-datadir`)

   **Windows:**
   ```bash
   divid -regnet=1 -daemon -datadir="%APPDATA%\DIVI\REGNET\node1\data" -rpcport=18332
   ```

   **macOS:**
   ```bash
   divid -regnet=1 -daemon -datadir="$HOME/Library/Application Support/DIVI/REGNET/node1/data" -rpcport=18332
   ```

   **Linux:**
   ```bash
   divid -regnet=1 -daemon -datadir="$HOME/.divi/REGNET/node1/data" -rpcport=18332
   ```

2. **Generate blocks**

   **Windows:** `divi-cli -regnet=1 -datadir="%APPDATA%\DIVI\REGNET\node1\data" generate 101`  
   **macOS:** `divi-cli -regnet=1 -datadir="$HOME/Library/Application Support/DIVI/REGNET/node1/data" generate 101`  
   **Linux:** `divi-cli -regnet=1 -datadir="$HOME/.divi/REGNET/node1/data" generate 101`

   The first blocks mature coinbase outputs so you can spend them.

3. **Use RPC** (same `-datadir` = path to node’s **data** directory)
   ```bash
   divi-cli -regnet=1 -datadir="<path-to-node1/data>" getblockcount
   divi-cli -regnet=1 -datadir="<path-to-node1/data>" getnewaddress
   ```

---

## Two-node setup

Two nodes on one machine: useful for testing sends between wallets or multi-node behavior.

Each node needs a **unique P2P port** (`-port`). Use **-datadir** pointing at each node’s **data** directory (e.g. `node1/data`). You can use **divi.conf** in each node root with `port` and `addnode`; then start with `-datadir=<path-to-node/data>`.

**Node 1** – e.g. generate blocks here. **Node 2** – e.g. recipient or second wallet.

1. **Start Node 1** (P2P 18444, RPC 18332). Use `-datadir=.../node1/data`.

   **Windows:** `divid -regnet=1 -daemon -wallet=node1.dat -datadir="%APPDATA%\DIVI\REGNET\node1\data" -port=18444 -rpcport=18332 -blockmintime=20`  
   **macOS:** `divid -regnet=1 -daemon -wallet=node1.dat -datadir="$HOME/Library/Application Support/DIVI/REGNET/node1/data" -port=18444 -rpcport=18332 -blockmintime=20`  
   **Linux:** `divid -regnet=1 -daemon -wallet=node1.dat -datadir="$HOME/.divi/REGNET/node1/data" -port=18444 -rpcport=18332 -blockmintime=20`

   `-blockmintime=20` makes block generation every 20 seconds when you call `generate`.

2. **Generate initial blocks on Node 1**  
   **Windows:** `divi-cli -regnet=1 -datadir="%APPDATA%\DIVI\REGNET\node1\data" generate 101`  
   **macOS:** `divi-cli -regnet=1 -datadir="$HOME/Library/Application Support/DIVI/REGNET/node1/data" generate 101`  
   **Linux:** `divi-cli -regnet=1 -datadir="$HOME/.divi/REGNET/node1/data" generate 101`

3. **Start Node 2** (P2P 18445, RPC 18333). Use `-datadir=.../node2/data`.

   **Windows:** `divid -regnet=1 -daemon -wallet=node2.dat -datadir="%APPDATA%\DIVI\REGNET\node2\data" -port=18445 -rpcport=18333`  
   **macOS:** `divid -regnet=1 -daemon -wallet=node2.dat -datadir="$HOME/Library/Application Support/DIVI/REGNET/node2/data" -port=18445 -rpcport=18333`  
   **Linux:** `divid -regnet=1 -daemon -wallet=node2.dat -datadir="$HOME/.divi/REGNET/node2/data" -port=18445 -rpcport=18333`

4. **Add peers (localhost:unique_port)**  
   Use the **P2P port** and **-datadir** = path to that node’s **data** directory.

   **From Node 1:** `divi-cli -regnet=1 -datadir="<path-to-node1/data>" addnode "127.0.0.1:18445" "add"`  
   **From Node 2:** `divi-cli -regnet=1 -datadir="<path-to-node2/data>" addnode "127.0.0.1:18444" "add"`

   If both run these, they are peers.

5. **Generate blocks and send between nodes**  
   On Node 1: `generate 1`. Get address from Node 2: `divi-cli -regnet=1 -datadir="<path-to-node2/data>" getnewaddress`. From Node 1: `divi-cli -regnet=1 -datadir="<path-to-node1/data>" sendtoaddress "<address>" <amount>`. Optionally `generate 1` on Node 1 to confirm.

---

## Three-node setup

Same idea: each node uses its **data** directory for `-datadir`, plus a unique **P2P port** and **RPC port**. Then add each other as peers.

| Node  | P2P port | RPC port | -datadir |
|-------|----------|----------|----------|
| node1 | 18444    | 18332    | .../node1/data |
| node2 | 18445    | 18333    | .../node2/data |
| node3 | 18446    | 18334    | .../node3/data |

1. **Start all three** with `-datadir=.../node1/data`, `.../node2/data`, `.../node3/data` and the ports above (see two-node section for full Windows/macOS/Linux commands).

2. **Generate blocks on node1** (e.g. `generate 101`).

3. **Add peers** (use each node’s **data** path for `-datadir`):

   **From Node 1:** `addnode "127.0.0.1:18445" "add"` and `addnode "127.0.0.1:18446" "add"`  
   **From Node 2:** `addnode "127.0.0.1:18444" "add"` and `addnode "127.0.0.1:18446" "add"`  
   **From Node 3:** `addnode "127.0.0.1:18444" "add"` and `addnode "127.0.0.1:18445" "add"`

   If all run these, they are fully connected.

---

## Flags reference

| Flag | Purpose |
|------|---------|
| `-regnet=1` | Run in REGNET (private chain). |
| `-daemon` | Run in background. |
| `-datadir=<path>` | Data directory for this node (blocks, chainstate, wallet). Use each node’s **data** directory (e.g. `node1/data`). |
| `-port=<port>` | P2P port for peer connections. Use a unique port per node when running multiple nodes (e.g. 18444, 18445, 18446). |
| `-rpcport=<port>` | RPC port (must be unique per node on one machine). |
| `-wallet=<name>.dat` | Wallet file name inside `datadir`. |
| `-blockmintime=20` | Block time in seconds when using `generate` (optional). |

To connect nodes as peers, use `addnode "127.0.0.1:<other node's -port>" "add"` from each node. If all nodes add the others, they are fully connected.

---

## Stopping nodes

```bash
divi-cli -regnet=1 -datadir="<path-to-node/data>" stop
```

Run once per node, with each node’s **data** directory.
