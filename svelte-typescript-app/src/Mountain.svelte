<script lang="ts">
  export let name: string;
  export let summited: boolean;
  $: summitBoxStyle = (summited ? 'box-summit-true' : 'box-summit-false');

  function summitButtonClick(){
    summited = !summited;
    console.log(summited);
  }
</script>

<main>
  <div class="box {summitBoxStyle}">
    {name} <button on:click="{ summitButtonClick }">登頂!</button>
    { summitBoxStyle }
  </div>
</main>

<style>
  .box {
    border: 0.1em;
    border-color: black;
    border-style: solid;
  }

  .box-summit-true {
    background-color: brown;
  }

  .box-summit-false {
    background-color: aqua;
  }

</style>