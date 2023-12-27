<script>
  import Team from './lib/Team.svelte'

  //variable declaration
  let red = 20
  let blue = 20
  let redTeam = ' red'
  let blueTeam = 'blue'
  let teamR = 'Red'
  let teamB = 'Blue'

  //reactive value declaration
  $: redPoints = red
  $: bluePoints = blue

  //function handlers

  function redHandler() {
    red += 1
  }

  function redSubHandler() {
    red -= 1
  }

  function bluePlusHandler() {
    blue += 1
  }

  function blueSubHandler() {
    blue -= 1
  }

  ///reset function handler

  function resetHandler() {
    redPoints = 20
    bluePoints = 20
  }
</script>

<header>MTG Counter App</header>
<main>
  <Team
    increaseHandler={redHandler}
    decreaseHandler={redSubHandler}
    teamName={teamR}
    number={redPoints}
    teamColor={redTeam}
  />
  <Team
    increaseHandler={bluePlusHandler}
    decreaseHandler={blueSubHandler}
    teamName={teamB}
    number={bluePoints}
    teamColor={blueTeam}
  />
</main>
<div class="container">
  <button class="btn-reset" on:click={resetHandler}>Reset Game</button>
</div>

<style>
  header {
    margin: 20px 0;
    text-align: center;
    font-weight: 900;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
  main {
    display: flex;
    flex: 1;
  }
  .container {
    position: absolute;
    left: 10%;
  }

  .container button {
    padding: 4px;
    width: 100%;
    font-weight: 900;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    background-color: orange;
    border: 1px solid grey;
  }
</style>
