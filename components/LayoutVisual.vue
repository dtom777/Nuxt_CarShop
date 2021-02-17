<template>
  <div
    class="relative pt-24 pb-32 flex content-center justify-center z-10"
    :style="`min-height: ${height}vh;`"
  >
    <div
      :class="`absolute top-0 w-full h-full bg-center bg-cover ${visual}`"
    ></div>
    <div class="container relative mx-auto">
      <div class="items-center">
        <div class="w-full px-4 mx-auto text-center">
          <h1 class="text-yellow-500 font-semibold md:text-4xl text-3xl title">
            {{ title }}
          </h1>
          <p v-if="message" class="text-white font-semibold text-lg title">
            {{ message }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LayoutVisual',
  props: {
    title: {
      type: String,
      default: '',
    },
    message: {
      type: String,
      default: '',
    },
    visual: {
      type: String,
      default: 'visual-home',
    },
    height: {
      type: Number,
      default: 53,
    },
  },
}
</script>

<style>
.visual-home {
  background-image: url('~@/assets/img/visual-home.jpg');
}
.visual-concept {
  background-image: url('~@/assets/img/visual-concept.jpg');
}
.visual-shop {
  background-image: url('~@/assets/img/visual-store.jpg');
}
.visual-menu {
  background-image: url('~@/assets/img/visual-menu.jpg');
}
.visual-information {
  background-image: url('~@/assets/img/visual-information.jpg');
}
.visual-error {
  background-image: url('~@/assets/img/visual-home.jpg');
}
.visual-chat {
  background-image: url('~@/assets/img/visual-chat.jpg') ;
}
.title {
  text-shadow: 0px 5px 3px darkgray;
}
h1 {
  font-family: 'Lobster', cursive;
}
</style>
