<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./pages/Home.svelte";
  import NewEmail from "./pages/NewEmail.svelte";

  // simple routing until we add a router library
  let route = window.location.pathname;

  // react to clicks
  const navigate = (path) => {
    history.pushState({}, "", path);
    route = path;
  };

  // handle back/forward
  window.onpopstate = () => {
    route = window.location.pathname;
  };
</script>

<Nav {navigate} />

{#if route === "/new"}
  <NewEmail />
{:else}
  <Home />
{/if}

<style>
@import './styles/global.css';
</style>
