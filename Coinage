Yes, you can calculate the age for each UTXO (Unspent Transaction Output) as a percentage and then find the average age for all of them.

Here's how you can approach it:

1. **Calculate the Age Percentage for Each UTXO**: Determine the age of each UTXO by examining the number of confirmations. You mentioned that the age maxes out at 10080 confirmations, so the age percentage for each UTXO would be:
   
   \(\text{Age percentage} = \frac{\text{Number of confirmations for UTXO}}{10080} \times 100\)

2. **Calculate the Weighted Age Percentage for Each UTXO**: Multiply the age percentage by the coin quantity for that UTXO. This will give you a weighted age percentage, taking into account the coin weight for that particular UTXO:
   
   \(\text{Weighted age percentage} = \text{Age percentage} \times \text{Coin quantity}\)

3. **Calculate the Total Coin Quantity**: Add up the coin quantities for all UTXOs. This will be used to find the average:

   \(\text{Total coin quantity} = \sum \text{Coin quantity for each UTXO}\)

4. **Calculate the Total Weighted Age Percentage**: Add up the weighted age percentages for all UTXOs:

   \(\text{Total weighted age percentage} = \sum \text{Weighted age percentage for each UTXO}\)

5. **Calculate the Average Age Percentage**: Divide the total weighted age percentage by the total coin quantity:

   \(\text{Average age percentage} = \frac{\text{Total weighted age percentage}}{\text{Total coin quantity}}\)

Note: This approach assumes that the weight of each UTXO is directly proportional to the coin quantity and that the age percentage is a linear function of the number of confirmations.

Here's a simple example to illustrate the process:

- UTXO 1: 5000 coins, 5040 confirmations
- UTXO 2: 5000 coins, 10080 confirmations

The calculations would be as follows:

- UTXO 1: Age percentage = \(50\%\), Weighted age percentage = \(50\% \times 5000 = 2500\)
- UTXO 2: Age percentage = \(100\%\), Weighted age percentage = \(100\% \times 5000 = 5000\)
- Total coin quantity = \(10000\)
- Total weighted age percentage = \(7500\)
- Average age percentage = \(\frac{7500}{10000} = 75\%\)

This result means that, on average, the coins are 75% "aged" based on the confirmation counts.
