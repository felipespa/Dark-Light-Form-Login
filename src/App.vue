<script setup lang="ts">
import { onMounted, ref } from "vue";

import ToggleTheme from "./components/ToggleTheme.vue";
import Form from "./components/Form.vue";

const isDarkMode = ref(false);

function setTheme(theme: string) {
  if (theme === "dark") localStorage.setItem("@toggle-theme:theme-1.0.0", "dark");
  else localStorage.setItem("@toggle-theme:theme-1.0.0", "light");

  document.querySelector("[color-theme]")?.setAttribute("color-theme", theme);
}

function handleThemeChange(colorTheme: boolean) {
  isDarkMode.value = colorTheme;
  setTheme(colorTheme ? "dark" : "light");
}

onMounted(() => {
  const userTheme = localStorage.getItem("@toggle-theme:theme-1.0.0");

  setTheme(userTheme ?? "light");
  isDarkMode.value = userTheme && userTheme === "dark" ? true : false;
});
</script>

<template>
  <main>
    <div class="home_container">
      <div class="image">
        <transition>
          <img src="./assets/images/dark.jpg" v-if="isDarkMode" />
          <img src="./assets/images/light.jpg" v-else />
        </transition>
      </div>

      <ToggleTheme @toggle-theme="handleThemeChange" :is-dark-mode="isDarkMode" />
      <Form />
    </div>
  </main>
</template>

<style scoped lang="scss">
main {
  width: 100vw;
  height: 100vh;
  background: var(--foreground);
  transition: 0.3s;

  .home_container {
    width: 60vw;
    height: 70vh;
    border-radius: 20px;

    position: fixed;
    inset: 15vh 20vw;

    display: flex;
    overflow: hidden;

    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    transform: translateY(-2px);

    .image {
      position: relative;
      max-width: 440px;
      width: 100%;
      height: 100%;

      img {
        max-width: 100%;
        display: block;
        object-fit: cover;
      }

      &::after {
        content: "";
        position: absolute;
        inset: 0;
        width: 100%;
        height: 100%;
        background: rgba(34, 33, 33, 0.2);
        z-index: 2;
      }
    }
  }
}
</style>
