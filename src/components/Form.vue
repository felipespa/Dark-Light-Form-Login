<script setup lang="ts"></script>

<template>
  <div class="form_container">
    <svg class="wave" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        fill="#F3F4F5"
        fill-opacity="1"
        d="M0,128L48,112C96,96,192,64,288,48C384,32,480,32,576,48C672,64,768,96,864,90.7C960,85,1056,43,1152,37.3C1248,32,1344,64,1392,80L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
      ></path>
    </svg>

    <hr />

    <div class="form_title">
      <h2>Faça parte dessa aventura!</h2>
      <span>Não tem uma conta? <strong>Cadastre-se</strong></span>
    </div>

    <hr />

    <form>
      <input type="text" placeholder="E-mail" />
      <input type="password" placeholder="Senha" />

      <button>CONTINUAR</button>
    </form>

    <hr />

    <div class="sign-in">
      <button><img src="../assets/images/google.png" /> Google</button>
      <button><img src="../assets/images/linkedin.png" /> Linkedin</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.form_container {
  width: 100%;
  height: 100%;
  letter-spacing: 0.043em;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  padding: 6rem 10rem;
  position: relative;
  z-index: 1;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;

  background: url("../assets/images/sun-rising3.jpg");
  background-position: center;
  background-size: cover;

  &::after {
    content: "";
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    /* background: rgba(255, 255, 255, 0.15); */
    backdrop-filter: blur(10px);
    background: var(--foreground);
    opacity: 0.6;
    z-index: -1;
  }

  .wave {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 58%;
    transform: rotate(180deg);
    z-index: -1;
    opacity: 0.66;
  }

  .form_title {
    color: #fff;
    margin-bottom: 2rem;
    h2 {
      font-weight: 600;
    }

    span {
      font-weight: 300;

      strong {
        font-weight: 600;
      }
    }
  }

  hr {
    width: 100%;
    opacity: 0.2;
    margin: 0.4rem auto;
    border-color: #fff;
  }

  form {
    display: flex;
    flex-direction: column;

    width: 100%;
    padding: 2rem 0;

    input {
      width: 100%;
      height: 46px;
      border-radius: 4px;
      padding: 0.4rem 1rem;
      background: rgba(233, 231, 231, 0.8);
      border: unset;
      font-weight: 500;

      &:first-child {
        margin-bottom: 1rem;
      }
    }

    button {
      background: var(--foreground);
      color: #fff;
    }
  }

  .sign-in {
    display: flex;
    justify-content: space-between;

    width: 100%;

    button {
      img {
        margin-right: 1rem;
      }

      &:first-child {
        margin-right: 1rem;
      }
    }
  }

  button {
    height: 46px;
    width: 100%;
    margin-top: 1rem;
    border-radius: 4px;
    background: #fff;
    box-shadow: 0 3px 1px -2px rgba(0, 0, 0, 0.2), 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 5px 0 rgba(0, 0, 0, 0.12) !important;
    font-weight: 500;
    letter-spacing: 0.0892857143em;
    outline: 0;
    text-decoration: none;
    text-indent: 0.0892857143em;
    border-style: unset;
    text-transform: uppercase;
    cursor: pointer;

    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
