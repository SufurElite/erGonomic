<script lang="ts">
  import logo from './assets/images/logo-universal.png'
  import {Greet} from '../wailsjs/go/main/App.js'
  import { InlineCalendar } from 'svelte-calendar';
	import dayjs from 'dayjs';

	const theme = {
		calendar: {
			width: '600px',
			shadow: '0px 0px 5px rgba(0, 0, 0, 0.25)'
		}
	};

	let store;


  let resultText: string = "Please enter your name below 👇"
  let name: string

  function greet(): void {
    Greet(name).then(result => resultText = result)
  }
</script>


<main>
  <img alt="Wails logo" id="logo" src="{logo}">
    <InlineCalendar bind:store {theme} />

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
</main>

<style>

  #logo {
    display: block;
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
