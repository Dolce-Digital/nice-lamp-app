<script>
  // Future: Fetch packs from engine
  let packs = [
    { id: "december", name: "December Magic", desc: "Cosy lights, festive vibes, winter charm." },
    { id: "spring", name: "Spring Bloom", desc: "Fresh air, blossoms, outdoor energy." },
    { id: "summer", name: "Summer Escape", desc: "Sun, terraces, beach, adventure." },
    { id: "autumn", name: "Autumn Warmth", desc: "Fireplaces, slow travel, comfort flavours." },
  ];
</script>

<div class="wrapper">
  <h1>Select a Seasonal Pack</h1>
  <p class="subtitle">Choose the mood or season you want to use as inspiration.</p>

  <div class="grid">
    {#each packs as pack}
      <div class="card" on:click={() => alert(`${pack.name} (Engine link coming soon!)`)}>
        <h3>{pack.name}</h3>
        <p>{pack.desc}</p>
      </div>
    {/each}
  </div>
</div>

<style>
.wrapper {
  max-width: 900px;
  margin: 60px auto;
  padding: 0 20px;
}

h1 {
  font-family: "Cormorant Garamond", serif;
  font-size: 2.4rem;
  margin-bottom: 12px;
  color: var(--nl-dark);
}

.subtitle {
  opacity: 0.8;
  margin-bottom: 32px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 28px;
}

.card {
  background: white;
  padding: 24px;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.06);
  cursor: pointer;
  transition: 0.2s ease;
}

.card:hover {
  background: var(--nl-light);
  transform: translateY(-4px);
  box-shadow: 0px 6px 14px rgba(0,0,0,0.08);
}

.card h3 {
  margin-bottom: 8px;
  font-family: "Cormorant Garamond", serif;
}
</style>
