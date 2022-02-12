<script>
    export let page = 'home';

    import Contact from "./Contact.svelte";
    import Home from './Home.svelte';
    import Schedule from './Schedule.svelte';
    import Activities from "./Activities.svelte";
    import Quotes from "./Quotes.svelte";
</script>

<nav>
    <ul>
        <li><a href="/" on:click|preventDefault={() => {page = 'home'}}>Startseite</a></li>
        <li><a href="/" on:click|preventDefault={() => {page = 'schedule'}}>Programm</a></li>
        <li><a href="/" on:click|preventDefault={() => {page = 'contact'}}>Kontakt</a></li>
        <li><a href="/" on:click|preventDefault={() => {page = 'activities'}}>Aktivitäten</a></li>
        <li><a href="/" on:click|preventDefault={() => {page = 'quotes'}}>Lieder/Zitate</a></li>
    </ul>
</nav>
<main>
    {#if page === 'schedule'}
        <Schedule/>
    {:else if page === 'contact'}
        <Contact/>
    {:else if page === 'activities'}
        <Activities/>
    {:else if page === 'quotes'}
        <Quotes/>
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