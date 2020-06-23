---
description: In process
---

# Easy Staking Parameters

{% hint style="warning" %}
Easy Staking is currently under construction and undergoing significant modifications. A demo app is deployed on Kovan for testing purposes. Current parameters subject to change.
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Value</th>
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
      <td style="text-align:left">TBD</td>
    </tr>
    <tr>
      <td style="text-align:left">Instant Withdrawal Fee</td>
      <td style="text-align:left">3%* + ETH gas fees</td>
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
      <td style="text-align:left">After ___ hours, funds are available to withdraw during the scheduled
        withdrawal window.</td>
    </tr>
    <tr>
      <td style="text-align:left">Scheduled Withdrawal Window</td>
      <td style="text-align:left">___ hours. Scheduled withdrawals are available to pull within this time
        period. If not withdrawn, they are returned to the protocol. <b>APR is not reset if returned</b>,
        funds continue to accrue emissions as before.</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking APR</td>
      <td style="text-align:left">
        <p>Up to 15%* APR based on 2 factors.
          <br />1. amount of time STAKE is locked in protocol (up to 7.5%)
          <br />2. total amount staked by all participants (up to 7.5%)</p>
        <p><em>&lt;link to sigmoid function when finalized&gt;</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Multiple Deposits</td>
      <td style="text-align:left">Supported. Each deposit event creates a separate deposit ID. Emission
        is accrued from time of deposit for each ID.</td>
    </tr>
    <tr>
      <td style="text-align:left">Partial Withdrawal Penalty</td>
      <td style="text-align:left">When a partial amount of any deposit (per deposit ID) is withdrawn, the
        time-based APR resets to 0.</td>
    </tr>
  </tbody>
</table>

_\*configurable_

