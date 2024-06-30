<script lang="ts">
  import { InlineCalendar } from 'svelte-calendar';
  import Settings  from './Settings.svelte';
  import Day from './Day.svelte';
  import AddTask from './AddTask.svelte';


	let theme = { calendar: { width:'70vw',
			shadow: '0px 0px 5px rgba(0, 0, 0, 0.25)'
		}
	};

	let store;
</script>


<main>
  <div id="app">
    <Settings />
      <div id = "main">
      <div id="cal">
        <InlineCalendar bind:store {theme} />
      </div>
    <Day store={store}/>
      </div>
    <AddTask/>

</main>

<style>
  #app {
    width:100%;
    height:100%;
    display:block;
    margin:auto;
    justify-items: center;
  }

  #main {
    display: flex;
    margin-top:5%;
    margin-bottom:2%;
    flex:row;
  }

  #cal {
  margin-left: 5%;


  }

</style>
