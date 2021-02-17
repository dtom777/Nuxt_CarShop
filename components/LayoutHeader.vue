<template>
  <header class="w-full absolute md:static bg-black px-2 py-2 z-50">
    <div class="md:max-w-3xl mx-auto md:flex md:items-center">
      <div
        class="w-full md:w-4/12 md:flex mx-auto px-6 flex justify-between items-center h-16"
      >
        <h1>
          <a
            class="text-white font-bold leading-relaxed inline-block whitespace-no-wrap text-3xl"
            href="/"
          >
          Nuxt_CarShop
          </a>
        </h1>
        <div class="text-white md:hidden md:justify-end">
          <button class="focus:outline-none" @click="isOpen = !isOpen">
            <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
              <path
                v-show="!isOpen"
                d="M24 6h-24v-4h24v4zm0 4h-24v4h24v-4zm0 8h-24v4h24v-4z"
              />
              <path
                v-show="isOpen"
                d="M24 20.188l-8.315-8.209 8.2-8.282-3.697-3.697-8.212 8.318-8.31-8.203-3.666 3.666 8.321 8.24-8.206 8.313 3.666 3.666 8.237-8.318 8.285 8.203z"
              />
            </svg>
          </button>
        </div>
      </div>
      <nav
        class="w-full md:block absolute left-0 md:static bg-black z-20"
        :class="isOpen ? 'block' : 'hidden'"
      >
        <ul class="md:flex md:justify-end md:items-end">
          <li class="w-full md:w-auto md:ml-5">
            <a
              href="/service/"
              class="text-white inline-block md:block md:py-0 py-5 md:px-0 px-5 w-full"
              >SERVICE</a
            >
          </li>
          <li class="w-full md:w-auto md:ml-5">
            <a
              href="/menu/"
              class="text-white inline-block md:block md:py-0 py-5 md:px-0 px-5 w-full"
              >LINE UP</a
            >
          </li>
          <li class="w-full md:w-auto md:ml-5">
            <a
              href="/contact/"
              class="text-white inline-block md:block md:py-0 py-5 md:px-0 px-5 w-full"
              >CONTACT</a
            >
          </li>
          <li class="w-full md:w-auto md:ml-5">
            <a
              href="/shop/"
              class="text-white inline-block md:block md:py-0 py-5 md:px-0 px-5 w-full"
              >SHOP</a
            >
          </li>
          <li class="w-full md:w-auto md:ml-5">
            <a
              href="/information/"
              class="text-white inline-block md:block md:py-0 py-5 md:px-0 px-5 w-full"
              >INFORMATION</a
            >
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'LayoutHeader',
  data() {
    return {
      isOpen: false,
    }
  },
}
</script>

<style>
h1 {
  font-family: 'Lobster', cursive;
}
</style>
