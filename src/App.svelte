<script>
  export let page = 'home';
  import Home from './Home.svelte';
  import Schedule from './Schedule.svelte';
</script>

<nav>
    <ul>
        <li><a href="/" on:click|preventDefault={() => {page = 'home'}}>Home</a></li>
        <li><a href="/" on:click|preventDefault={() => {page = 'schedule'}}>Schedule</a></li>
    </ul>
</nav>
<main>
  {#if page === 'schedule'}
    <Schedule/>
  {:else}
    <Home/>
  {/if}
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>