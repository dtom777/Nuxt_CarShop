<template>
  <layout-wrapper>
    <layout-visual
      title="Nuxt_CarShop"
      message="Nuxt.jsとfirebaseとmicroCMS"
    ></layout-visual>
    <!-- menu -->
    <div class="w-full md:max-w-full mx-auto mt-10">
      <base-heading>Recommend</base-heading>
      <div class="md:flex flex-nowrap mb-5 md:mb-0">
        <layout-menu-list
          v-for="(item, index) in menuItems"
          :id="item.id"
          :key="index"
          :image="item.image"
          :image-url="item.image.url"
          :name="item.name"
          :spec="item.spec"
          item-class="w-full md:mb-10 shadow-xl bg-white"
          block-class="max-w relative"
          image-class=""
          data-class="w-full h-full absolute top-0 left-0 text-white transiton opacity-0 hover:opacity-100 flex justify-center items-center text-opacity-75"
          name-class="text-4xl font-bold "
          :flag-body="false"
        />
      </div>
    </div>
    <base-button name="Line upを見る" link="/chat/" />
    <!-- information -->
    <div class="mt-10">
      <base-heading>Infotmation</base-heading>
      <div class="mb-5">
        <layout-information-list
          v-for="(item, index) in infoItems"
          :id="item.id"
          :key="index"
          :date="item.date"
          :title="item.title"
          :image="item.image"
          :image-url="item.image.url"
        />
      </div>
      <base-button
        name="Information一覧を見る"
        link="/information/"
        class-margin="mt-10"
      />
    </div>
  </layout-wrapper>
</template>

<script>
import axios from 'axios'
import LayoutWrapper from '~/components/LayoutWrapper.vue'
export default {
  components: { LayoutWrapper },
  async asyncData({ $config }) {
    const menu = await axios.get(
      `${$config.apiUrl}/menu?limit=3&filters=flag[equals]true`,
      {
        headers: { 'X-API-KEY': $config.apiKey },
      }
    )
    const info = await axios.get(`${$config.apiUrl}/information?limit=3`, {
      headers: { 'X-API-KEY': $config.apiKey },
    })
    return {
      menuItems: menu.data.contents,
      infoItems: info.data.contents,
    }
  },
}
</script>
