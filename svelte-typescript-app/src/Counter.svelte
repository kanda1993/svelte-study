<script lang="ts">
  let count: number=0;

  function countUp(){
    count += 1;
  }
</script>

<main>
  <button on:click="{ countUp }">
    Counter :
    { count }
  </button>

</main>
