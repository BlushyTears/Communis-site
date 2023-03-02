<script>
  import DropdownBtn from "../lib/Button.svelte";
</script>

<p class="dashboard-title">Communis Dashboard</p>
<h3 class="dashboard-sub-title"> Smart Contract Address: 0x5A9780Bfe63f3ec57f01b087cD65BD656C9034A8 </h3>

<!-- https://codepen.io/SoufianeLasri/pen/QjRrQz Cool loader for loading hex stakes -->

<!-- 
Start day
(Click to sort ascending)	
Staked Days
(Click to sort ascending)	
Due Day
(Click to sort ascending)	
T-Shares
(Click to sort ascending)	
Max payout
(Click to sort ascending)	
Available Start Bonus (COM)
(Click to sort ascending)	
Available End Bonus (COM)
(Click to sort ascending)	
Mint COM -->

<div class="flex-container">
  <div class="info-container">
    <div class="communis-stakes-container">
      <br />
      <!-- 15,823,758,674,856,123 COM< -->
      <h2 class="staked-communis-title">Staked COM:</h2>
      <h2 class="staked-communis-title">15,823,758,674 COM</h2>
    </div>
    <div class="communis-stakes-container">
      <br />
      <h2 class="staked-communis-title">End Bonus debt:</h2>
      <h2 class="staked-communis-title">52,236,215 COM</h2>
    </div>
  </div>

  <div class="info-container">
    <div class="communis-stakes-container">
      <br />
      <!-- 15,823,758,674,856,123 COM< -->
      <h2 class="staked-communis-title">Restake obligations:</h2>
      <h2 class="staked-communis-title">None</h2>
    </div>
    <div class="communis-stakes-container">
      <br />
      <h2 class="staked-communis-title">Share rate: </h2>
      <h2 class="staked-communis-title">246,592</h2>
    </div>
  </div>
</div>

<div class="hex-stakes-container">
  <h2 class="current--hex-stakes-title">Current Stakes</h2>
  <table class="stakes-table">
    <thead>
      <tr>
        <th>Start Day</th>
        <th>Staked Days</th>
        <th>Due Day</th>
        <th>T-Shares</th>
        <th>Max Payout</th>
        <th>Available Start Bonus</th>
        <th>Available End Bonus</th>
        <th>Mint</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>5</td>
        <td>550</td>
        <td>555</td>
        <td>52.5</td>
        <td>506,500</td>
        <td>123,125,125,918</td>
        <td>123,125,125,918</td>
        <td>
          <DropdownBtn />
        </td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td>62</td>
        <td>1256</td>
        <td>1318</td>
        <td>12.5</td>
        <td>250,125</td>
        <td>123,125,125</td>
        <td>0</td>
        <td>
          <DropdownBtn />
        </td>
      </tr>
    </tfoot>
  </table>
</div>

<style>

  .dashboard-title {
    font-size: calc(1.2vw + 3rem);
    color: var(--white);
    margin-top: 5rem;
    margin-bottom: 0;
  }

  .dashboard-sub-title {
    margin-bottom: 5rem;
    color: var(--white);
    font-size: calc(0.5vw + 0.5rem);
    text-align: center;
    line-height: 1;
  }

  .flex-container {
    margin-bottom: 5rem;
    display: flex;
    align-items: center;
  }

  .communis-stakes-container {
    background-color: var(--black-blue);
    margin-left: 1.2rem;
    margin-right: 1.2rem;
    display: flex;
    font-size: 1.2rem;
    line-height: 2.2rem;
    border-radius: 7px;
  }

  .staked-communis-title {
    color: var(--white);
    margin-left: 1rem;
    margin-right: 1rem;
  }

  /* Style the hex-stakes-container */
  .hex-stakes-container {
    margin: 20px;
    padding: 20px;
    background-color: var(--black-blue);
    color: var(--white);
    border: 1px solid var(--gray);
    border-radius: 7px;
    max-width: 1200px;
    overflow-x: auto;
  }

  /* Style the current--hex-stakes-title */
  .current--hex-stakes-title {
    font-size: 24px;
    color: var(--white);
    margin-top: 0;
    margin-bottom: 20px;
  }

  /* Style the table headers */
  .stakes-table th {
    width: auto;
    text-align: left;
    padding: 8px;
    background-color: var(--dark-gray);
    color: var(--white);
    border-bottom: 1px solid #ddd;
  }

  /* Style the table rows */
  .stakes-table tr {
    border-bottom: 1px solid #ddd;
  }

  /* Style the table data */
  .stakes-table td {
    text-align: left;
    padding: 12px;
  }

  td {
    font-size: 1.5rem;
  }
  tr {
    font-size: 1.5rem;
  }

  p {
    margin-top: 5rem;
    text-align: center;
    font-size: 5em;
    line-height: 1;
  }

  @media screen and (max-width: 700px) {
    .communis-stakes-container {
      font-size: 2.5vw;
      line-height: 4vw;
    }
  }

  @media screen and (max-width: 900px) {
    .flex-container {
      display: block;
    }
    .communis-stakes-container {
      font-size: 2vw;
      margin-bottom: 1rem;
    }
  }
</style>
