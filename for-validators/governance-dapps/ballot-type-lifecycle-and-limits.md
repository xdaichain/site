---
description: A Ballot is a proposal that changes the current state of the network.
---

# Ballot Type, Lifecycle & Limits

## Ballot Properties

* **Ballot Type**:
  * **`Keys Ballot`**: add, remove, or swap any type of validator's key: mining, voting, payout. This ballot is used to add a new validator or remove a current validator.
  * **`Consensus Threshold`**: change minimum consensus threshold \(total votes required\) for `Keys Ballot` and `Consensus Threshold Ballot`.
  * **`Proxy`**: change the addresses of smart contract implementations
  * **`Emission Funds`**: Send, burn or freeze accumulated emission funds 
* **Ballot End Time:** Defines the time window in which the Ballot is open for voting. Currently, this must be a date/time in the future that allows a reasonable time for other validators to consider, research, and discuss the ballot.  The format is `mm/dd/yyyy, hh:mm AM/PM` \(local time\), for example, `02/22/2022, 10:00 PM`.   
* **Consensus Threshold**: Defines the minimum number of votes required for a Ballot to succeed.  Once a ballot has been created this value is immutable. The minimum threshold for Keys and Consensus Threshold Ballots is determined through the `Consensus Threshold Ballot`. The threshold for `Proxy` and `Emission Funds` ballots is always calculated based on validator\_count. This threshold is equal to `(validators_count - master_of_ceremony) / 2 + 1` \(we exclude the Master of Ceremony \(MoC\) from the validator set count because the MoC cannot vote\).

## Ballot Lifecycle

* **Created**: A new ballot has been created.
* **Open**: The time window where the Ballot will accept votes.  **NOTE:** _A Validator can only vote once per ballot, and the MoC does not possess any voting rights._
* **Closed awaiting Finalization**: When the `Ballot End Time` expires, the ballot no longer accepts any new votes,  but it has not yet been committed to the network.
* **Finalized**: After a ballot has expired it must be Finalized, i.e. the proposer or another active validator in the associated network must click the "Finalize" button on the ballot.  This commits the result of the ballot to the network, and if the ballot was accepted, the changes are applied to to the network.

## Ballot Limits

Limits exist for each ballot type to prevent malicious validators from spamming the network. We  use the following formula to determine active votes per validator: 

\[200/N\] where N= `NumberOfActiveValidators` \(excluding Master of Ceremony\).  For Example with 21 Total Active Validators:  200 / 21 = 9 \(as an integer\) - 9 is the maximum active ballots allowed to one Validator.  As the number of validators increases, this number is reduced.

 The current limit is 13 active ballots \(200/15\) at one time for each type of ballot \(_Updated 11/21/19_\) .

{% hint style="info" %}
Ballots need to be thoughtful and should only be proposed by a validator if they can defend the ballot and explain the ballot's benefit to the network. Inappropriate use or abuse of balloting privileges, or failure of a validator to participate in proposed ballots, can be cited in future balloting procedures.
{% endhint %}

