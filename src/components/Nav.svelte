<script>
  export let navigate;
</script>

<nav class="navbar">
  <div class="brand" on:click={() => navigate("/")}>
    Nice-Lamp ConciergeEmail
  </div>

  <div class="nav-links">
   <a class={$page.url.pathname === "/" ? "active" : ""} href="/">Home</a>
<a class={$page.url.pathname.startsWith("/new") ? "active" : ""} href="/new">New Email</a>
<a class={$page.url.pathname.startsWith("/packs") ? "active" : ""} href="/packs">Seasonal Packs</a>
    <a href="#" on:click|preventDefault={() => alert("Account system coming later")}>Account</a>
  </div>
</nav>

<style>
a.active {
  font-weight: bold;
  border-bottom: 2px solid #D84171;
}
</style>
<style>
/* (same CSS as before) */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 18px 32px;
  background: white;
  border-bottom: 1px solid rgba(0,0,0,0.07);
}

.brand {
  font-family: "Cormorant Garamond", serif;
  font-size: 1.6rem;
  color: var(--nl-dark);
  border-bottom: 3px solid rgba(216, 65, 113, 0.25);
  cursor: pointer;
}

.nav-links {
  display: flex;
  gap: 24px;
}

.nav-links a {
  font-size: 0.95rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  opacity: 0.85;
}
.nav-links a:hover {
  opacity: 1;
  color: var(--nl-pink);
}
</style>
