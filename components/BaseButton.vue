<template>
  <div :class="`${classPosition} ${classMargin} mb-5 mx-auto`">
    <a
      :href="link"
      :class="`block shadow-xl py-4 md:mx-8 mx-4  ${classShape} ${classBackGroundColor} ${classBackGroundHoverColor} ${classTextColor} md:text-lg md:font-bold font-semibolds`"
      >{{ name }}</a
    >
  </div>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    name: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
    classPosition: {
      type: String,
      default: 'text-center',
    },
    classMargin: {
      type: String,
      default: '',
    },
    classShape: {
      type: String,
      default: '',
    },
    classBackGroundColor: {
      type: String,
      default: 'bg-yellow-700',
    },
    classBackGroundHoverColor: {
      type: String,
      default: 'hover:bg-opacity-50',
    },
    classTextColor: {
      type: String,
      default: 'text-white',
    },
  },
}
</script>
