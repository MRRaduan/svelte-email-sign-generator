<script>
  import { area, fullname, cargo, phone } from "../stores.js";
</script>

<style>
  .form-group {
    display: flex;
    flex-direction: column;
    padding: 10px 0;
  }
  .input-title {
    display: block;
    text-align: left;
    font-size: 20px;
    font-weight: 700;
    font-family: "Montserrat", sans-serif;
  }

  .input-field {
    margin-top: 6px;
    width: 100%;
    font-size: 20px;
    border: none;
    border-radius: 5px;
    padding: 10px 20px;
    position: relative;
    transition: all 0.15s ease-in-out;
  }

  .input-field:focus {
    transform: translate3d(0, -3px, 0);
    transition: all 0.15s ease-in-out;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
  }
</style>

<div>
  <form class="main-form">
    <div class="form-group">
      <label for="name" class="input-title">Nome</label>
      <input
        type="text"
        name="name"
        class="input-field"
        bind:value={$fullname} />
    </div>
    <div class="form-group">
      <label for="cargo" class="input-title">Função</label>
      <input type="text" name="cargo" class="input-field" bind:value={$cargo} />
    </div>
    <div class="form-group">
      <label for="phone" class="input-title">Telefone</label>
      <input type="text" name="phone" class="input-field" bind:value={$phone} />
    </div>
    <div class="form-group">
      <label for="cargo" class="input-title">Time ou área de atuação</label>
      <input type="text" name="cargo" class="input-field" bind:value={$area} />
    </div>
  </form>

</div>
