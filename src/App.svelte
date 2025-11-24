<script>
  import Nav from "./components/Nav.svelte";
  import Home from "./pages/Home.svelte";
  import NewEmail from "./pages/NewEmail.svelte";
  import Packs from "./pages/Packs.svelte";

  let route = window.location.pathname;

  const navigate = (path) => {
    history.pushState({}, "", path);
    route = path;
  };

  window.onpopstate = () => {
    route = window.location.pathname;
  };
</script>

<Nav {navigate} />

{#if route === "/new"}
  <NewEmail />
{:else if route === "/packs"}
  <Packs />
{:else}
  <Home />
{/if}

<style>
@import './styles/global.css';
</style>
