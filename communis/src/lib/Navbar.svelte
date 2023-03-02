<!-- <div class="topnav">
  <a class="button" href="http://localhost:5173/home/">Home</a>
  <a class="button" href="http://localhost:5173/dashboard/">Dashboard</a>
  <a class="button" href="http://localhost:5173/learn/">Learn</a>
  <a class="button" href="http://localhost:5173/telegram/">Telegram</a>
</div>
 -->
<script>
  export let name;
  export let nav_link_extern;
  export let icon = "";

  let isActive = false;

  function handleClick() {
  // Turn off active state for all buttons
  const buttons = document.querySelectorAll('.tab-btn');
  buttons.forEach((button) => {
    button.classList.remove('active');
  });

  // Turn on active state for the clicked button
  this.classList.add('active');
}
</script>

<!-- Checks if navbar buttons are for internal navigation or external links -->
{#if nav_link_extern == "False"}
<div class="logoWithBtn">
  <img class="logo" src={icon} alt="logo">
  <a href="/#/{name}/" > <button class="tab-btn" class:active={isActive} on:click={handleClick}>{name}</button> </a>
</div>
{:else if name == "Telegram"}
<div class="logoWithBtn">
  <img class="logo" src={icon} alt="logo">
  <a href="https://t.me/CommunisCrypto" target="noreferrer">
    <button class="tab-btn" class:active={isActive} on:click={handleClick}> <u>{name}</u></button>
  </a>
</div>
{:else if name == "Audit"}
<div class="logoWithBtn">
  <img class="logo" src={icon} alt="logo">
  <a href="https://www.certik.com/projects/communis" target="noreferrer">
    <button class="tab-btn" class:active={isActive} on:click={handleClick}><u>{name}</u></button>
  </a>
</div>
{/if}

<style>
  .logoWithBtn {
    display: flex;
    align-items: center;
  }

  .logo {
    width: 2rem;
    height: 2rem;
   }

  .tab-btn {
    font-family: sans-serif;
    font-size: calc(0.10vw + 1.5rem);
    color: var(--light-yellow);
    background-color: var(--invisible-color);
    border: none;
    border-radius: 4px;
    margin-right: 1rem;
    cursor: pointer;
  }

  .tab-btn.active {
    font-size: calc(0.25vw + 1.8rem);
    font-weight: bold;
  }

  .tab-btn:hover {
    color: var(--light-yellow-hover);
  }

</style>
