<script>
  export let teamName = 'Name'
  export let number = 20
  export let teamColor = 'black'
  export let increaseHandler
  export let decreaseHandler
  let disable = false

  function addHandler() {
    increaseHandler()
  }

  function subtractHandler() {
    decreaseHandler()
  }
</script>

<div class="row" style="color:{teamColor}">
  <h4>Team {teamName}: <span>{number}</span></h4>
  <div class="column">
    <button on:click={addHandler} class="btn btn-1">+</button>
    <button on:click={subtractHandler} class="btn btn-2">-</button>
  </div>
  {#if number === 0}
    <h5>{teamName} team is the winner</h5>
    <style>
      .btn {
        pointer-events: none;
      }
    </style>
    {#if teamName === 'Red'}
      <style>
        .row {
          color: rgba(255, 0, 0, 0.2);
        }
      </style>
    {:else if teamName === 'Blue'}
      <style>
        .row {
          color:.row {
            color: rgba(0, 0, 255, 0.2);
          }
        }
      </style>
    {/if}
  {/if}
</div>

<style>
  .row {
    margin: 20px 5px;
    border: 2px dashed;
    width: 40%;
    padding-bottom: 10px;
    display: flex;
    flex: 1;
  }
  h5 {
    text-align: center;
    margin-top: 5px;
  }

  h4 {
    text-align: center;
    font-weight: bold;
  }
  .column {
    text-align: center;
    align-items: center;
  }
  .btn-1 {
    background-color: green;
    color: white;
  }
  .btn-2 {
    background-color: red;
    color: white;
  }
</style>
