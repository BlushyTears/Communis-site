<script>
  // HEX Codes: Hex Codes: #003049 // #d62828 // #f77f00 // #fcbf49 // #eae2b7

  let bonuses = [
    {
      name: "Mint Start Bonus",
      description: "You get a 10% freemium quantity of COM For beginning a HEX stake.",
      open: false,
    },
    {
      name: "Mint End Bonus",
      description: "You get the remaining 90% COM For ending the same HEX stake.",
      open: false,
    },
    {
      name: "Mint Good Accounting Bonus",
      description: "You can claim free COM for cleaning stale HEX T-shares using the good accounting",
      open: false,
    },
    {
      name: "Mint Restake Bonus",
      description: "You get to claim free COM by restaking and maintaining your shares",
      open: false,
    },
  ];

  function toggleBonus(index) {
    bonuses = bonuses.map((bonus, i) => {
      if (i === index) {
        return { ...bonus, open: !bonus.open };
      } else {
        return bonus;
      }
    });
  }
</script>

<div class="upper-container">
  <div class="section">
    <h1>Got a HEX stake over 180 days?</h1>
    <p>
      Congratulations! You are eligible to claim your free $COM <a
        href="#/dashboard/">HERE</a
      >!
      <br />
      <br />
      If not, you can easily create a HEX stake
      <a href="https://www.hex.com/">HERE</a> and later claim your FREE $COM.
    </p>
  </div>
</div>

<div class="section-middle">
  <p>
    ● Your influence in Communis is reflected from your T-Shares you have and
    from your stakes & days.
    <br />
    <br />
    ● Communis aims to run alongside Hex to instill positive staking habits in the
    community.
    <br />
    <br />
    ● Completely read-only: No wrapping stakes, No Encapsulating of your stakes.
    <br />
    <br />
    ● Mintable only to stakes whose ownership can be provably signed for.
    <br />
    <br />
    ● No admin keys and no additional Origin Address
    <br />
    <br />
    ● No extra found-me-first bonuses.
  </p>
</div>

<div class="section-bottom">
  <p class="paragraph-title">Terminology</p>

  {#each bonuses as bonus, index}
    <h1 class="collapse-paragraph" on:click={() => toggleBonus(index)}>
      {bonus.name}
    </h1>
    {#if bonus.open}
      <p>{bonus.description}</p>
    {/if}
  {/each}
</div>

<style>
  .logo {
    opacity: 0.7;
    width: 100%;
    height: 100%;
  }
  .collapse {
    display: none;
  }

  .upper-container {
    background-color: var(--red);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 5rem;
    padding: 1rem;
  }

  p {
    text-align: center;
    font-size: 1.5em;
    line-height: 2rem;
    resize: none;
  }

  .paragraph-title {
    text-align: center;
    font-size: 2.5em;
    line-height: 2rem;
    resize: none;
  }

  h1 {
    text-align: center;
    line-height: 1;
  }

  .collapse-paragraph {
    background-color: var(--yellow);
    color: white;
    padding: 15px;
    cursor: pointer;
  }

  .collapse-paragraph:hover {
    background-color: var(--red);
    transition: 0.2s;
  }

  h2 {
    text-align: center;
    line-height: 1;
  }

  .section-middle {
    padding: 1rem;
    background-color: var(--blue);
  }
</style>
