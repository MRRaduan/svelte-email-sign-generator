<script>
  import { area, fullname, cargo, phone } from "./stores.js";
  import { fly, fade } from "svelte/transition";
  import PageTitle from "./components/PageTitle.svelte";
  import SignForm from "./components/SignForm.svelte";
  import SignTable from "./components/SignTable.svelte";

  let signTable;

  let isCopied = false;

  const copySign = () => {
    let range = document.createRange();
    range.selectNodeContents(signTable);

    window.getSelection().removeAllRanges();
    window.getSelection().addRange(range);

    let copyTable = document.execCommand("copy");
    window.getSelection().removeRange(range);
    isCopied = true;
  };
</script>

<style>
  .main-content {
    display: block;
    position: absolute;
    width: 100%;
    min-height: 100vh;
    background-color: #f1e8d9;
    padding-top: 40px;
  }
  .container {
    width: 100%;
    max-width: 600px;
    display: block;
    margin: 0 auto;
    padding: 40px 0 0 0;
  }
  .sign-card {
    background-color: #fff;
    width: 100%;
    max-width: 410px;
    padding: 30px 40px;
    border-radius: 5px;
    margin: 20px auto 0 auto;
  }
  .btn-primary {
    margin: 20px auto 0 auto;
    display: block;
    background-color: #ca2430;
    border: none;
    font-family: "Montserrat", sans-serif;
    font-size: 18px;
    font-weight: bold;
    text-transform: uppercase;
    padding: 10px 20px;
    border-radius: 4px;
    color: #f1e8d9;
    border-left: solid #eeb566 5px;
    border-bottom: solid #eeb566 5px;
    cursor: pointer;
    transition: all 0.1s ease-in;
  }
  .btn-primary:active {
    transform: translate3d(0, 5px, 0);
    transition: all 0.1s ease-in;
  }

  .message-copied {
    font-family: "Montserrat", sans-serif;
    color: #ca2430;
    padding: 10px;
    font-size: 18px;
    margin-top: 15px;
    text-align: center;
    font-weight: bold;
    text-transform: uppercase;
    border-radius: 5px;
  }
</style>

<main class="main-content">
  <PageTitle />
  <div class="container">
    <SignForm />

    <div class="sign-card" bind:this={signTable}>
      <SignTable />
    </div>
    {#if $fullname !== '' && $cargo !== '' && $area !== '' && $phone !== ''}
      <button
        class="btn-primary"
        in:fly={{ x: -50, duration: 320 }}
        out:fade
        on:click={copySign}>
        copiar assinatura
      </button>
    {/if}

    {#if isCopied}
      <div class="message-copied" in:fly={{ y: 50, duration: 200 }}>
        Copiado! &#128077;
      </div>
    {/if}
  </div>
</main>
