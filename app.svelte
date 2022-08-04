<script lang="ts">
  //animations
  import { fade, draw } from 'svelte/transition';
  //the value that changes each   time we click on one of these
  let value = 0;
  //the necessary functions
  function decrease(){
    value-=1;
    if (value == -1) {
      re()
    }
  }
  function increase(){
    value+=1; 
  }
  function re(){
    value = 0;
  }
</script>

<style>
  #num{
    background-color: blue;
    color: whitesmoke;
    width: 250px;
    height: 250px;
    font-size: 200px;
    text-align: center;
    font-family: monospace;
  }
  #inc{
    background: green;
    width: 100px;
    height: 33px;
  }
  #dec{
    background: red;
    width: 100px;
    height: 33px;
  }
  #re{
    background: blue;
    width: 100px;
    height: 33px;
  }


</style>

<div id="num">
  <p transition:fade>{value}</p>
</div>
<button id="inc" on:click={increase}>Increase</button>
<button id="dec" on:click="{decrease}">Decrease</button>
<button id="re" on:click="{re}">Reset</button>
