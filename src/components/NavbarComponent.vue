<template>
  <div class="flex-center-row container">
    <h1>OX</h1>
    <SearchbarComponent />
    <div class="icons-menu flex-center-row" @click="handleShowDepartment">
      <span class="material-symbols-outlined"> menu </span>
    </div>
    <div class="icons flex-center-row">
      <span class="material-symbols-outlined"> person </span>
      <span class="material-symbols-outlined"> repeat </span>
      <span class="material-symbols-outlined"> favorite </span>
      <span class="material-symbols-outlined cart">
        local_mall
        <span class="flex-center-row">1</span>
      </span>
    </div>
  </div>
</template>

<script>
import SearchbarComponent from './SearchbarComponent.vue'

export default {
  components: { SearchbarComponent },
  name: 'ChallengeNavbarComponent',
  props: ['handleShowDepartment'],

  data() {
    return {}
  },

  mounted() {},

  methods: {}
}
</script>

<style lang="css" scoped>
.container {
  justify-content: space-between;
  padding: 0 200px;
}
.icons-menu {
  display: none;
  background: var(--pm-blue-light);
  padding: 5px;
  cursor: pointer;
}
h1 {
  font-weight: 700;
}
.icons {
  color: var(--sc-white);
  gap: 25px;
}
.icons span {
  font-size: 25px;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}
.icons span:hover {
  color: var(--pm-white);
}
.cart {
  position: relative;
}
.cart > span {
  width: 15px;
  height: 15px;
  position: absolute;
  color: #000;
  font-size: 10px;
  font-weight: 800;
  border-radius: 50%;
  bottom: -5px;
  right: -5px;
  font-family: Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  /* padding: 5px; */
  background: var(--pm-white);
}
@media screen and (min-width: 1272px) {
  .container {
    padding: 0 200px;
  }
}
@media screen and (max-width: 1272px) {
  .container {
    padding: 0 50px;
  }
}
@media screen and (max-width: 980px) {
  .container {
    padding: 0 10px;
  }
  .icons {
    display: none;
  }
  .icons-menu {
    display: flex;
  }
}
@media screen and (max-width: 444px) {
  .container {
    justify-content: center;
  }
  h1 {
    display: none;
  }
  .icons-menu {
    display: none;
  }
}
</style>
