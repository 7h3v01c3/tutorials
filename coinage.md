# COIN AGE and how its calculated

COIN AGE is a critical factor in some hybrid Proof of Work (PoW)/Proof of Stake (PoS) mining protocols, serving as a mechanism to discourage malicious activities and promote fairness within the system. This approach draws inspiration from Satoshi's original concept but implements a virtualized mining process that embraces the beneficial competitive nature of PoW while introducing a multiplier to the calculations and a notarization process which finalizes the PoS work.

In this context, the multiplier is determined by the quantity of coins in a UTXO, also known as the weight. The process to calculate the average age of UTXOs, considering their weight, can be formalized as follows:


1. **Calculate the Age Percentage for Each UTXO**: Determine the age of each UTXO by examining the number of confirmations. The age maxes out at 10080 confirmations, so the age percentage for each UTXO would be:

    $\text{Age percentage} = \frac{\min\left(\text{Number of confirmations for UTXO}, 10080\right)}{10080} \times 100$

   Here, we're using the minimum function to ensure that the age percentage doesn't exceed 100%. If the number of confirmations exceeds 10080, the age percentage is capped at 100%.

2. **Calculate the Weighted Age Percentage for Each UTXO**: Multiply the age percentage by the coin quantity for that UTXO:
   
   $\text{Weighted age percentage} = \text{Age percentage} \times \text{Coin quantity}$

3. **Calculate the Total Coin Quantity**: Add up the coin quantities for all UTXOs:

   $\text{Total coin quantity} = \sum \text{Coin quantity for each UTXO}$

4. **Calculate the Total Weighted Age Percentage**: Add up the weighted age percentages for all UTXOs:

   $\text{Total weighted age percentage} = \sum \text{Weighted age percentage for each UTXO}$

5. **Calculate the Average Age Percentage**: Divide the total weighted age percentage by the total coin quantity:

   $\text{Average age percentage} = \frac{\text{Total weighted age percentage}}{\text{Total coin quantity}}$

Here's a simple example:

- UTXO 1: 5000 coins, 5040 confirmations
- UTXO 2: 5000 coins, 10080 confirmations

The calculations would be as follows:

- UTXO 1: Age percentage = $50\%$, Weighted age percentage = $50\% \times 5000 = 2500$
- UTXO 2: Age percentage = $100\%$, Weighted age percentage = $100\% \times 5000 = 5000$
- Total coin quantity = $10000$
- Total weighted age percentage = $7500$
- Average age percentage = $\frac{7500}{10000} = 75\%$

This result means that, on average, the coins are 75% "aged" based on the confirmation counts.

