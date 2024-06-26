<script lang="ts">
  import logo from './assets/images/logo-universal.png'
  import {Greet} from '../wailsjs/go/main/App.js'
  import { InlineCalendar } from 'svelte-calendar';
  import Settings  from './Settings.svelte';
	import dayjs from 'dayjs';

	const theme = {
		calendar: {
      width:"80vw",
			shadow: '0px 0px 5px rgba(0, 0, 0, 0.25)'
		}
	};

	let store;


</script>


<main>
  <div id="app">
    <Settings />
    <img alt="Wails logo" id="logo" src="{logo}">
    <div>
      <div >
    <InlineCalendar bind:store {theme} />
        </div>
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

  #logo {
    width: 50%;
    height: 50%;
    margin: auto;
    padding: 10% 0 0;
    background-position: center;
    background-repeat: no-repeat;
    background-size: 100% 100%;
    background-origin: content-box;
  }

  .result {
    height: 20px;
    line-height: 20px;
    margin: 1.5rem auto;
  }

  .input-box .btn {
    width: 60px;
    height: 30px;
    line-height: 30px;
    border-radius: 3px;
    border: none;
    margin: 0 0 0 20px;
    padding: 0 8px;
    cursor: pointer;
  }

  .input-box .btn:hover {
    background-image: linear-gradient(to top, #cfd9df 0%, #e2ebf0 100%);
    color: #333333;
  }

  .input-box .input {
    border: none;
    border-radius: 3px;
    outline: none;
    height: 30px;
    line-height: 30px;
    padding: 0 10px;
    background-color: rgba(240, 240, 240, 1);
    -webkit-font-smoothing: antialiased;
  }

  .input-box .input:hover {
    border: none;
    background-color: rgba(255, 255, 255, 1);
  }

  .input-box .input:focus {
    border: none;
    background-color: rgba(255, 255, 255, 1);
  }

</style>
