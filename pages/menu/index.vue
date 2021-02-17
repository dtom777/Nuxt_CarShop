<template>
  <layout-wrapper>
    <layout-visual title="Line up" message="商品ラインナップ" :height="53" visual="visual-menu" />
    <div class="container w-full mt-5 mx-auto">
      <div class="mb-10">
        <layout-line-up
          v-for="(item, index) in items"
          :id="item.id"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :price="item.price"
          :spec="item.spec"
          :flag-body="false"
        />
      </div>
    </div>
    <base-button name="トップに戻る" link="/" />
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
import LayoutLineUp from '~/components/LayoutLineUp.vue'

export default {
  components: { LayoutLineUp },
  async asyncData({ $config }) {
    const { data } = await axios.get(`${$config.apiUrl}/menu`, {
      headers: { 'X-API-KEY': $config.apiKey },
    })
    return {
      items: data.contents,
    }
  },
  head() {
    return {
      title: 'メニュー',
    }
  },
}
</script>
