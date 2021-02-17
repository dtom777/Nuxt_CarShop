<template>
  <div class="bg-black text-white">
    <div class="border-t border-b px-10 py-4">
      <p class="md:text-lg">お問い合わせ・商談希望はこちらまで</p>
      <div class="md:font-bold font-semibold md:text-xl">
        <p class="mb-3"><font-awesome-icon icon="phone-alt"/> 090-xxxx-xxxx</p>
        <a href="/contact/" class="border bg-white text-black py-2 px-2 rounded-lg hover:bg-opacity-50"><font-awesome-icon icon="envelope"/> メールでのお問い合わせ</a>
      </div>
    </div>
    <footer class="py-3">
      <p class="text-center text-sm">Copyright &copy; 2020 Tom</p>
    </footer>
  </div>
</template>

<script>
import BaseButton from './BaseButton.vue'
export default {
  components: { BaseButton },
  name: 'LayoutFooter',
}
</script>
