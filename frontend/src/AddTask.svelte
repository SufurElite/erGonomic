<script lang="ts">
import Icon from '@iconify/svelte';
let showAddTask = false;

</script>


<div>
{#if showAddTask}
<div id = "add-task-screen">
    <div id="top-row-task"> 
        <h2> Add Task </h2>
    </div>
      <div id="exit-icon" on:click={()=>showAddTask= false}> 
        <Icon icon="mdi:alpha-x-box" style="height: 3em; width: auto" />
      </div>


</div>
{/if}

  <div id="bottom-row" style="background-color: #36454F;">
    <div id="icon" on:click={()=>showAddTask= true}> 
      <Icon icon="mdi:add-circle" style="height: 3em; width: auto" />
    </div>
  </div>
</div>


<style>

#top-row-task{
width:40%;
margin-left:30%;
border-bottom: solid 3px orange;
}

  #bottom-row {
    height: 10%;
    width: 100%;
    margin: auto;
    justify-content: center;
    align-items: center;
    margin-bottom: 0%;
}

#add-task-screen {
background-color:#5f788a;
position: absolute;
margin-left:10%;
width: 80%;
height: 80%;
margin-top:15%;
top:0;
z-index:10;
border-radius: 25px;

}

#icon {
    margin-left:90%;
  }

#exit-icon {
position:absolute;
bottom:0;
margin-left:90%;
  }


</style>
