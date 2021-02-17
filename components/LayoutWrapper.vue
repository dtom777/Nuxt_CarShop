<template>
  <div class="wrapper">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'LayoutWrapper',
}
</script>

<style scoped>
.wrapper {
  padding-top: 80px;
  background-color: #000;
  padding-bottom: 1rem;
  @media (min-width: 768px) {
    padding-top: 0px;
  }
}
</style>
