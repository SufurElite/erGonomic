<script lang="ts">
import Icon from '@iconify/svelte';
import dayjs from 'dayjs';
export let store;

</script>


<div id="schedule">
  <div id="date-row">
    <Icon icon="mdi:invoice-schedule" style="height: 1.5em; width: auto" />
		<h3> {dayjs($store?.selected).format('MM/DD/YYYY')} </h3>
  </div>
</div>

<style>

#schedule {
width:20vw;
display: flex;
justify-content: center;
margin-left: 2.5%;
margin-right: 2.5%;
}

  #date-row {
    height: 10%;
    width: 100%;
    display:flex;
    flex-direction:row;
    justify-content: center;
    align-items: center;
    text-align:justify;
    border-bottom: solid 3px orange;
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
margin:auto;

  }

</style>
