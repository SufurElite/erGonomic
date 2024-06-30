<script lang="ts">
  import { InlineCalendar } from 'svelte-calendar';
  import Settings  from './Settings.svelte';
  import Day from './Day.svelte';
	import dayjs from 'dayjs';

function down() {size -= 5;}
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

<div class="grid">
	<button on:click={() => store.add(-1, 'year')}>-1y</button>
	<button on:click={() => store.add(-1, 'month')}>-1m</button>
	<button class="day" on:click={() => store.add(-1, 'day')}>-1d</button>
	<p>
		{dayjs($store?.selected).format('MM/DD/YYYY')}
	</p>
	<button class="day" on:click={() => store.add(1, 'day')}>+1d</button>
	<button on:click={() => store.add(1, 'month')}>+1m</button>
	<button on:click={() => store.add(1, 'year')}>+1y</button>
</div>
          <div>
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
    flex:row;
  }

  #cal {
  margin-left: 5%;


  }

</style>
