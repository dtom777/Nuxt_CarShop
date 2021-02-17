<template>
  <layout-wrapper>
    <layout-visual
      title="Line up"
      message="商品ラインナップ"
      :height="53"
      visual="visual-menu"
    />
    <div class="container max-w-3xl w-full mt-5 mx-auto">
      <div class="mb-10 text-white text-2x mx-2">
        <h2>
          ~{{ item.name }}~
        </h2>
        <img v-if="item.image" :src="item.image.url" :alt="item.name" class="w-full" />
        <div class="my-2 text-base">
          {{ item.body }}
        </div>
        <!-- eslint-disable-next-line vue/no-v-html-->
        <div class="mb-10 text-base" v-html="item.spec"></div>
      </div>
    </div>
    <base-button name="Line upに戻る" link="/menu/" />
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $config, params, error }) {
    try {
      const { data } = await axios.get(
        `${$config.apiUrl}/menu/${params.id}`,
        {
          headers: { 'X-API-KEY': $config.apiKey },
        }
      )
      return {
        item: data,
      }
    } catch (err) {
      error({
        errorCode: 404,
      })
    }
  },
  head() {
    return {
      title: this.item.title,
    }
  },
}
</script>
