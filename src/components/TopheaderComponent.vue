<template>
  <div class="wrapper flex-center-row">
    <div class="links-container flex-center-row">
      <router-link to="http://location" class="flex-center-row">
        <span class="material-symbols-outlined"> location_on </span>
        Find Store
      </router-link>
      <router-link to="http://location" class="flex-center-row">
        <span class="material-symbols-outlined"> mail </span>
        support@ox.com
      </router-link>
    </div>
    <div class="links-container flex-center-row">
      <router-link to="http://location">Contact</router-link>
      <span class="line"></span>
      <router-link to="http://location">Track Your Order</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChallengeTopheaderComponent',

  data() {
    return {}
  },

  mounted() {},

  methods: {}
}
</script>

<style lang="css" scoped>
.wrapper {
  width: 100%;

  justify-content: space-between;
  /* background: #; */
  border-bottom: 1px solid var(--sc-white-dark);
  padding: 5px 200px;
}
@media screen and (min-width: 1272px) {
  .wrapper {
    padding: 0 200px;
  }
}
@media screen and (max-width: 1272px) {
  .wrapper {
    padding: 0 50px;
  }
}
a {
  color: var(--sc-white);
}
a span {
  color: var(--sc-white-dark);
  margin-right: 10px;
  font-size: 15px;
}
.links-container:first-of-type {
  gap: 40px;
}
.links-container:last-of-type .line {
  width: 2px;
  background: var(--sc-white);
  height: 15px;
  margin: 0 10px;
}
@media screen and (max-width: 980px) {
  .wrapper {
    display: none;
  }
}
</style>
