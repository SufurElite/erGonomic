<script lang="ts">
import Icon from '@iconify/svelte';
import { fade } from "svelte/transition"
let showSettings = false;

</script>


<div>
  <div id="top-row" style="background-color: #36454F;">
    <div style="position:relative;">
          <h1>erGonomic</h1>
    </div>
    <div id="icon" on:click={()=>showSettings = true}> 
      <Icon icon="mdi:settings-outline" style="height: 3em; width: auto" />
    </div>
  </div>
</div>
{#if showSettings}
<div id = "settings-screen">
    <div id="top-row"> 
    <h2> Settings </h2>
      <div id="icon" on:click={()=>showSettings = false}> 
        <Icon icon="mdi:exit-to-app" style="height: 3em; width: auto" />
      </div>
    </div>

</div>
{/if}

<style>

  #top-row {
    height: 10%;
    width: 100%;
    margin: auto;
    display:flex;
    flex-direction:row;
    justify-content: center;
    align-items: center;
    margin-bottom: 0%;
}

#settings-screen {
background-color:#5f788a;
position: absolute;
width: 100%;
height: 80%;
margin-top:15%;
top:0;
z-index:10;
border-radius: 25px;
}
  #icon {
    position:absolute;
    margin-top:auto;
    margin-bottom:auto;
    margin-left:90%;
  }

</style>
