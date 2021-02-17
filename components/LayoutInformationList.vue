<template>
  <div class="md:mx-4 mx-2 border-b bg-white">
    <a :href="'/information/' + id + '/'" class="block px-4 py-3">
    <div class="flex">
      <img v-if="image" :src="imageUrl" :class="imageClass" />
      <div class="ml-4 md:text-xl text-">
        <time class="block text-gray-600 md:py-4">{{ date | formatDate }}</time>
        <div class="font-bold">{{ title }}</div>
      </div>
    </div>
    </a>
  </div>
</template>

<script>
export default {
  name: 'LayoutInformation',
  props: {
    title: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
    id: {
      type: String,
      required: true,
    },
    image: {
      type: Object,
      required: true,
    },
    imageUrl: {
      type: String,
      required: true,
    },
    imageClass: {
      type: String,
      default: 'w-1/3 md:h-auto h-20',
    }
  },
}
</script>
