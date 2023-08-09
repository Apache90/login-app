<script>
  let username = "";
  let password = "";
  let isLoggedIn = false;

  function login() {
    if (username === "franco" && password === "123") {
      isLoggedIn = true;
    } else {
      alert("Credenciales incorrectas");
    }
  }

  function logout() {
    isLoggedIn = false;
  }
</script>

<main>
  <div class="center-container">
    <div class="login-card">
      {#if !isLoggedIn}
        <div class="login-form">
          <h2>LOGIN</h2>
          <p>Por favor ingresa tus datos</p>
          <input
            type="text"
            bind:value={username}
            placeholder="Nombre de usuario"
          />
          <input
            type="password"
            bind:value={password}
            placeholder="Contraseña"
          />
          <button on:click={login}>Iniciar sesión</button>
        </div>
      {:else}
        <div class="welcome-message">
          <h2>Bienvenido {username}!</h2>
          <button on:click={logout}>Cerrar sesión</button>
        </div>
      {/if}
    </div>
  </div>
</main>

<style>
  .center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  .login-card {
    background-color: #ffffff;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 300px;
  }

  .login-form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .login-form input {
    width: 210px;
    margin-bottom: 10px;
    padding: 8px;
  }

  .login-form button {
    width: 230px;
    margin-bottom: 10px;
    padding: 8px;
  }

  .login-form h2,
  p {
    color: #333;
  }

  .welcome-message h2 {
    color: #333;
  }

  button {
    background-color: #007bff;
    color: #ffffff;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;
  }

  button:hover {
    background-color: #0056b3;
  }
</style>
