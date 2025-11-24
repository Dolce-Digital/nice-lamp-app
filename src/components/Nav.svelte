<nav class="navbar">
  <div class="brand">Nice-Lamp ConciergeEmail</div>

  <div class="nav-links">
    <a href="/">Home</a>
    <a href="/new">New Email</a>
    <a href="/packs">Packs</a>
    <a href="#">Account</a>
  </div>
</nav>

<style>
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
