<script>
  let purpose = "";
  let language = "en";
  let guestName = "";
  let stayDates = "";
  let tone = "soft";
</script>

<div class="wrapper">
  <h1>Start a New Email</h1>

  <p class="subtitle">
    Tell us what kind of email you want to create.  
    The ConciergeEmail engine will do the rest.
  </p>

  <div class="form">

    <!-- PURPOSE -->
    <label>Email Type</label>
    <select bind:value={purpose}>
      <option value="">Select purpose…</option>
      <option value="prestay">Pre-Stay Welcome Email</option>
      <option value="instay">In-Stay Concierge Email</option>
      <option value="poststay">Post-Stay Thank You</option>
      <option value="seasonal">Seasonal Update (Hotel → List)</option>
      <option value="announcement">Hotel Announcement</option>
    </select>

    <!-- LANGUAGE -->
    <label>Language</label>
    <select bind:value={language}>
      <option value="en">English</option>
      <option value="fr">French</option>
      <option value="de">German</option>
      <option value="nl">Dutch</option>
    </select>

    <!-- GUEST NAME -->
    <label>Guest Name (optional)</label>
    <input
      type="text"
      placeholder="e.g. Mr. Klein"
      bind:value={guestName}
    />

    <!-- DATES -->
    <label>Stay Dates (optional)</label>
    <input
      type="text"
      placeholder="Dec 7–10"
      bind:value={stayDates}
    />

    <!-- TONE -->
    <label>Tone</label>
    <select bind:value={tone}>
      <option value="soft">Soft Luxury</option>
      <option value="romantic">Chic Romance</option>
      <option value="neutral">Modern Minimal</option>
      <option value="warm">Warm & Friendly</option>
    </select>

    <button class="cta">
      Continue →
    </button>

  </div>
</div>

<style>
.wrapper {
  max-width: 640px;
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

.form {
  background: white;
  padding: 32px;
  border-radius: 14px;
  border: 1px solid rgba(0,0,0,0.06);
  display: flex;
  flex-direction: column;
  gap: 20px;
}

label {
  font-size: 0.95rem;
  font-weight: 600;
  opacity: 0.85;
}

select, input {
  padding: 12px;
  border-radius: 8px;
  border: 1px solid rgba(0,0,0,0.15);
  font-size: 1rem;
  background: #fff;
}

.cta {
  background: var(--nl-pink);
  color: white;
  padding: 14px 24px;
  font-size: 1.05rem;
  font-weight: 600;
  border-radius: 10px;
  margin-top: 12px;
  width: 100%;
}

.cta:hover {
  background: #B93463;
  box-shadow: 0px 4px 14px rgba(216, 65, 113, 0.25);
}
</style>
