# Emission Rates

STAKE Emissions are minted at a total of 15% APR. Emissions are split between Stakers and Liquidity Providers \(LP\). Two factors determine the % accrued for each group.

* **Time-based**: 7.5% total APR, split between Stakers and LPs. The amount of time an individual deposit has been staked in Easy Staking. A longer staking time for a deposit results in a higher APR for the Staker. Rewards for Stakers increase rapidly during the first several months and level out over time as they approach the 7.5% max based on a [sigmoid function](https://www.desmos.com/calculator/2xtimbnzqw). 
* **Supply-based**: 7.5% total APR, split between Stakers and LPs. The total amount of STAKE in the pool from all Stakers. Larger amounts result in a higher APR for Stakers. Rewards increase in relation to the total amount staked vs the total supply \(or by a factor between 0% and 100% of the total supply \(`totalSupplyFactor`\) if STAKE supply is a lot more than all STAKE holders currently have\).

## Examples

If a scheduled \(timed\) withdrawal with 0% fee occurs at the time-based point, the following rewards apply. If an instant withdrawal is processed, a fee is assessed on the total amount \(deposit + emissions\) and sent to the Liquidity Providers contract address prior to withdrawal.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Staker Deposit Amount</th>
      <th style="text-align:left">Time-based (tb)</th>
      <th style="text-align:left">Staker
        <br />tb
        <br />APR</th>
      <th style="text-align:left">Supply-
        <br />based (sb)</th>
      <th style="text-align:left">Staker
        <br />sb
        <br />APR</th>
      <th style="text-align:left">Staker Receives</th>
      <th style="text-align:left">LPs Receive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1000 STAKE</td>
      <td style="text-align:left">28 days</td>
      <td style="text-align:left">4.53%</td>
      <td style="text-align:left">2.134M out of 8.538M staked</td>
      <td style="text-align:left">1.875%</td>
      <td style="text-align:left">
        <p>4.91 STAKE
          <br />
        </p>
        <p><code>1000 * (4.53 + 1.875) / 100 * 28 / 365</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>6.59 STAKE
          <br />
        </p>
        <p><code>1000 * (15-(4.53 + 1.875)) / 100 * 28 / 365</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">5000 STAKE</td>
      <td style="text-align:left">48 days</td>
      <td style="text-align:left">5.99%</td>
      <td style="text-align:left">2.134M out of 4.269M staked (totalSupplyFactor of 50% employed)</td>
      <td
      style="text-align:left">3.75%</td>
        <td style="text-align:left">
          <p>64.04 STAKE</p>
          <p></p>
          <p><code>5000 * (5.99 + 3.75) / 100 * 48 / 365</code>
          </p>
        </td>
        <td style="text-align:left">
          <p>34.58 STAKE</p>
          <p></p>
          <p><code>5000 * (15-(5.99 + 3.75)) / 100 * 48 / 365</code>
          </p>
        </td>
    </tr>
  </tbody>
</table>

