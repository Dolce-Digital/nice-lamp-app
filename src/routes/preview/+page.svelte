<script>
  // Props passed via query params (later via store or navigation)
  import { page } from '$app/stores';

  // Extract JSON passed during navigation
  let emailData = {};
  $: if ($page?.data?.email) {
    emailData = $page.data.email;
  }

  function copyEmail() {
    const text = `
Subject: ${emailData.subject}

${emailData.preheader}

${emailData.body?.join("\n\n")}

${emailData.cta?.label}: ${emailData.cta?.url}

${emailData.signature}
    `;
    navigator.clipboard.writeText(text);
    alert("Email copied!");
  }
</script>

<style>
  .container {
    display: flex;
    gap: 2rem;
    padding: 2rem;
  }
  .sidebar {
    width: 260px;
    background: #ffffff;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 0 14px rgba(0,0,0,0.05);
  }
  .email-card {
    flex: 1;
    background: #ffffff;
    padding: 2rem;
    border-radius: 12px;
    box-shadow: 0 0 14px rgba(0,0,0,0.06);
  }
  h2, h3 {
    font-family: "Cormorant Garamond", serif;
  }
  .subject {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }
  .cta {
    padding: 0.75rem 1.2rem;
    background: #D84171;
    color: white;
    display: inline-block;
    border-radius: 6px;
    margin-top: 1rem;
    text-decoration: none;
  }
</style>

<div class="container">
  
  <!-- SIDEBAR -->
  <div class="sidebar">
    <h3>Flow Summary</h3>
    <p><strong>Season:</strong> {$page?.data?.season || 'Unknown'}</p>
    <p><strong>Language:</strong> EN</p>
    
    <button on:click={copyEmail}>Copy Email</button>
    <br><br>
    <button disabled>Regenerate (coming soon)</button>
    <br><br>
    <button disabled>Download .txt (coming soon)</button>
  </div>

  <!-- EMAIL PREVIEW -->
  <div class="email-card">
    <h2 class="subject">{emailData.subject}</h2>
    <em>{emailData.preheader}</em>
    <hr>

    {#each emailData.body as block}
      <p>{block}</p>
    {/each}

    {#if emailData.cta}
      <a class="cta" href={emailData.cta.url}>{emailData.cta.label}</a>
    {/if}

    <hr style="margin-top:2rem;">
    <p>{emailData.signature}</p>
  </div>

</div>
