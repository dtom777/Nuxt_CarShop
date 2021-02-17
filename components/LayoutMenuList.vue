<template>
  <div :class="itemClass">
    <div :class="blockClass">
      <a :href="'/menu/' + id + '/'">
        <img v-if="image" :src="imageUrl" :alt="name" :class="imageClass" />
        <div :class="dataClass" class="mask">
          <div :class="nameClass">
            {{ name }}
          </div>
          <p v-if="flagBody" class="mb-2 text-sm md:text-base">{{ body }}</p>
          <p class="md:font-medium mb-2 text-center">{{ price }}</p>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LayoutMenuList',
  props: {
    itemClass: {
      type: String,
      default: 'md:w-full mb-5 shadow-lg mx-auto text-center',
    },
    blockClass: {
      type: String,
      default:
        'md:w-full bg-white flex flex-wrap md:py-2',
    },
    imageClass: {
      type: String,
      default: 'w-full md:w-2/5',
    },
    dataClass: {
      type: String,
      default: 'w-full h-full md:leading-relaxed　bg-black',
    },
    nameClass: {
      type: String,
      default: 'md:font-bold font-semibold md:text-lg md:mb-5 mb-0 text-center'
    },
    flagBody: {
      type: Boolean,
      default: true,
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
    name: {
      type: String,
      required: true,
    },
    price: {
      type: String,
    },
  },
}
</script>

<style>
.mask {
	background-color:	rgba(0,0,0,0.4);
	-webkit-transition:	all 0.2s ease;
	transition:		all 0.2s ease;
}
</style>
