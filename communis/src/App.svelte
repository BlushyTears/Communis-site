<script>
  import logo from "./assets/com_logo.png";
  import homeicon from "./assets/home.png"
  import learnicon from "./assets/learn.png"
  import dashboardicon from "./assets/dashboard.png"
  import telegramicon from "./assets/telegram.png"
  import auditicon from "./assets/audit.png"

  import Router, { link } from "svelte-spa-router";
  import Navbar from "./lib/Navbar.svelte";
  import Content from "./routes/Content.svelte";
  import Dashboard from "./routes/Dashboard.svelte";
  import Learn from "./routes/Learn.svelte";
  import NotFound from "./routes/NotFound.svelte";
  import Animation from "./lib/Animation.svelte";

  export let name = "Communis";
  export let tickerSymbol = "COM";

  // HEX Codes: Hex Codes: #003049 // #d62828 // #f77f00 // #fcbf49 // #eae2b7

  let btnNames = ["Home", "More", "Dashboard", "Audit", "Telegram"];

  const routes = {
    "/": Content,

    "/home/": Content,

    "/More/": Learn,

    "/Dashboard/": Dashboard,

    "*": NotFound,
  };
</script>

<!-- <Hexagon/> -->
<!-- 
    <img class="logo" src={logo} alt="logo">
    <a href="/#/home/" ><img class="logo" src={logo}></a>
    <a href="/#/home/" ><h1 class="title">{name}</h1></a> -->

<div class="animation-container">
  <Animation/>
</div>

<div class="container">
  <a href="/#/home/">
    <div class="title-container">
      <img class="logo" src={logo} alt="logo">
       <h1 class="title">{name}</h1>
    </div>
  </a>
  <div class="navbar">
    <Navbar name={btnNames[0]} nav_link_extern={"False"} icon={homeicon}/>
    <Navbar name={btnNames[1]} nav_link_extern={"False"} icon={learnicon}/>
    <Navbar name={btnNames[2]} nav_link_extern={"False"} icon={dashboardicon}/>
    <Navbar name={btnNames[3]} nav_link_extern={"True"} icon={auditicon}/>
    <Navbar name={btnNames[4]} nav_link_extern={"True"} icon={telegramicon}/>
  </div>
  <Router {routes} />
</div>

<style>

  .animation-container {
    position: fixed;
    z-index: -1;
  }
  a {
    text-decoration: none;
  }
  .title-container{
    display: flex;
  }

  .logo {
    text-decoration: none;
    margin-left: 2rem;
    padding-top: 2rem;
    width: 119px;
    height: 100px;
  }
  .title {
    padding-top: 1rem;
    font-size: calc(0.5vw + 4rem);
  }
  .navbar {
    display: flex;
    justify-content: center;
  }
  .container {
    z-index: 999;
    background-color: var(--dark-gray-transparent);
    margin-left: 3rem;
    margin-right: 3rem;
    margin-bottom: 3rem;
    padding-bottom: 5rem;
  }

  @media screen and (max-width: 900px) {
    .navbar {
      display: grid;
    }
  }
</style>
