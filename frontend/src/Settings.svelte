<script lang="ts">
import Icon from '@iconify/svelte';

</script>


<div>
  <div id="top-row">
    <div style="flex:1; position:fixed; text-align:center;">
          <h1>erGonomic</h1>
    </div>
    <div id="icon">
      <Icon icon="mdi:settings-outline" style="height: 3em; width: auto" />
    </div>
  </div>
  
</div>

<style>

  #top-row {
    background-color:#36454F;
    position:fixed;
    height: 10%;
    width: 100%;
    margin: auto;
    display:flex;
    flex-direction:row;
    justify-content: center;
    align-items: center;
}
  #icon {
    margin-left:95%;
    margin-top:auto;
    margin-bottom:auto;
    position: fixed;
  }

</style>
