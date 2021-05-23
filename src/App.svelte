<script>
  import logo from './assets/svelte-logo.png'
  import {Route} from 'tinro'; 

  import Magazine from './Magazine.svelte'

  import { onMount } from 'svelte';
  import { createScene } from "./scene";
  onMount(() => {
    createScene()
  });
</script>



<main>
  <h1>Hello planet!</h1>
  <p>
    <a href="/">Home</a>
    |
    <a href="/magazine/">Magazine</a>
  </p>
  
  <div id="bg"></div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }
  #bg{
    position: fixed;
    z-index: -10;
    top: 0;
    left: 0;
  }
  img {
    height: 16rem;
    width: 16rem;
  }
  h1 {
    color: #00ff3e;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }
  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }
  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }
    p {
      max-width: none;
    }
  }
</style>

<Route path="/"></Route>
<Route path="/magazine/*">
    <Route path="/">
        <Magazine />
    </Route>
</Route>