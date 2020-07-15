---
description: In process
---

# EasyStaking Parameters

{% hint style="warning" %}
Easy Staking is currently under construction and undergoing significant modifications. A demo app is deployed on Kovan for testing purposes. Current parameters subject to change.
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Value - Definitions</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Github Repository</td>
      <td style="text-align:left"><a href="https://github.com/xdaichain/easy-staking-contracts">https://github.com/xdaichain/easy-staking-contracts</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Front-end Application</td>
      <td style="text-align:left"><a href="https://easy-staking.herokuapp.com/">https://easy-staking.herokuapp.com/</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Minimum STAKE Deposit</td>
      <td style="text-align:left">10^-18 (0.000000000000000001 STAKE)</td>
    </tr>
    <tr>
      <td style="text-align:left">Maximum STAKE Deposit</td>
      <td style="text-align:left">No Maximum</td>
    </tr>
    <tr>
      <td style="text-align:left">Instant Withdrawal Fee</td>
      <td style="text-align:left">2%* + ETH gas fees</td>
    </tr>
    <tr>
      <td style="text-align:left">Instant Withdrawal Availability</td>
      <td style="text-align:left">STAKE returned to wallet immediately</td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Fee</td>
      <td style="text-align:left">
        <p>0% + ETH gas fees. Requires 2 transactions</p>
        <p>1. Prepare withdrawal
          <br />2. Process during the scheduled withdrawal window.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Availability</td>
      <td style="text-align:left">After 12 hours, funds are available to withdraw during the scheduled withdrawal
        window (also 12 hours). STAKE price is the price when withdrawn, not price
        when withdrawal is scheduled.</td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Window</td>
      <td style="text-align:left">12 hours. Scheduled withdrawals are available to pull within this time
        period. If not withdrawn, they are returned to the protocol. <b>APR is not reset if returned</b>,
        funds continue to accrue emissions as before.</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking APR</td>
      <td style="text-align:left">
        <p>Up to 15%* APR based on 2 factors.
          <br />1. amount of time STAKE is locked in protocol (up to 7.5% based on sigmoid
          function)
          <br />2. total amount staked by all participants (up to 7.5%, based on a linear
          function)</p>
        <p><em>&lt;link to sigmoid functions when finalized&gt;</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Multiple Deposits</td>
      <td style="text-align:left">Supported. <b>Each deposit event creates a separate deposit ID, you cannot manually add additional STAKE to a current deposit, a new ID is created for each deposit</b>.
        Emission is accrued from time of deposit for each ID.</td>
    </tr>
    <tr>
      <td style="text-align:left">Partial Withdrawals</td>
      <td style="text-align:left">Supported. User can withdraw a partial amount from any deposit, and will
        receive the withdrawal amount + APR calculated at time of withdrawal. The
        remaining deposit amount will continue to accrue APR from that point forward.</td>
    </tr>
    <tr>
      <td style="text-align:left">Pending Withdrawal</td>
      <td style="text-align:left">A withdrawal has been scheduled for a deposit. The window to process the
        withdrawal is not yet open.</td>
    </tr>
    <tr>
      <td style="text-align:left">Eligible for Withdrawal</td>
      <td style="text-align:left">The withdrawal window is open and a scheduled withdrawal is available
        for processing. Users can enter the amount to withdraw and claim.</td>
    </tr>
  </tbody>
</table>

_\*configurable_

