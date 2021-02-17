<template>
  <div :class="itemClass">
    <div :class="blockClass">
      <a :href="'/menu/' + id + '/'">
        <div class="flex flex-wrap justify-between">
          <img v-if="image" :src="imageUrl" :alt="name" :class="imageClass" />
          <div :class="dataClass">
            <div>
              <div :class="nameClass">
                {{ name }}
              </div>
              <p class="font-medium md:text-xl text-white">
                {{ price }}
              </p>
              <h6 class="mt-4 md:text-lg text-md text-gray-500">※詳細はクリック</h6>
            </div>
          </div>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LayoutLineUp',
  props: {
    itemClass: {
      type: String,
      default: 'md:max-w-2xl mb-4 mx-auto',
    },
    blockClass: {
      type: String,
      default:
        'border flex flex-wrap justify-between mx-2',
    },
    imageClass: {
      type: String,
      default: 'w-1/2',
    },
    dataClass: {
      type: String,
      default: 'w-1/2 leading-relaxed　bg-black flex justify-center items-center',
    },
    nameClass: {
      type: String,
      default: 'font-bold md:text-3xl text-xl mb-4 text-yellow-500'
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
    spec: {
      type: String,
    }
  },
}
</script>
