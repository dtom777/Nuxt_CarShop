<template>
  <layout-wrapper>
    <layout-visual
      title="Information"
      message="お知らせ"
      :height="53"
      visual="visual-information"
    />
    <div class="w-full md:max-w-4xl my-8 mx-4 pt-8 pb-1 px-4 bg-black text-white">
      <h2 class="text-xl pb-2 border-b border-yellow-500 border-solid font-bold">
        {{ item.title }}
      </h2>
      <div class="pt-4 mb-4">
        <time class="block text-gray-400 mb-1">
          {{ item.date | formatDate }}
        </time>
      </div>
      <!-- eslint-disable-next-line vue/no-v-html-->
      <div class="mb-10" v-html="item.body"></div>
    </div>
    <base-button name="一覧に戻る" link="/information/" />
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $config, params, error }) {
    try {
      const { data } = await axios.get(
        `${$config.apiUrl}/information/${params.id}`,
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
