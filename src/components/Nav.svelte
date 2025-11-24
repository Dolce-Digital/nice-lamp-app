<script>
  import { page } from "$app/stores";
</script>

<nav class="navbar">
  <div class="brand">Nice-Lamp ConciergeEmail</div>

  <div class="nav-links">
    <a class={$page.url.pathname === "/" ? "active" : ""} href="/">Home</a>

    <a class={$page.url.pathname.startsWith("/new") ? "active" : ""} href="/new">
      New Email
    </a>

    <a class={$page.url.pathname.startsWith("/packs") ? "active" : ""} href="/packs">
      Packs
    </a>

    <a href="#" on:click|preventDefault={() => alert("Account coming soon")}>Account</a>
  </div>
</nav>

<style>
/* ACTIVE STATE */
a.active {
  font-weight: bold;
  border-bottom: 2px solid #D84171;
  color: #D84171;
}

/* NAV STYLES */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 18px 32px;
  background: white;
  border-bottom: 1px solid rgba(0,0,0,0.07);
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
  text-decoration: none;
  color: #392B21;
}

.nav-links a:hover {
  opacity: 1;
  color: #D84171;
}
</style>
