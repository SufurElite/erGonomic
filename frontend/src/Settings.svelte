<script lang="ts">
import Icon from '@iconify/svelte';

</script>


<div>
  <div id="top-row">
    <div style="position:relative;">
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
    height: 10%;
    width: 100%;
    margin: auto;
    display:flex;
    flex-direction:row;
    justify-content: center;
    align-items: center;
    margin-bottom: 10%;
}
  #icon {
    position:absolute;
    margin-top:auto;
    margin-bottom:auto;
    margin-left:90%;
  }

</style>
