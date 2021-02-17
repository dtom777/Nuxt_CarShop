<template>
  <layout-wrapper>
    <layout-visual title="Service" message="サービス内容" :height="53" visual="visual-concept" />
    <div class="w-full md:max-w-3xl mx-auto mt-10 mb-5 px-6 md:px-0 text-white">
      <h2 class="md:text-2xl text-lg font-bold text-center mb-5 text-yellow-500">
        あなたにとってのスペシャルがある場所
      </h2>
      <p class="text-center">
        車のことならなんでもご相談下さい。<br>
        お客様とともに最高の方向性を見つけ出し、<br>
        カーライフのサポーターとして全力で完全燃焼したいと思います。<br>
        どなたでもお気軽にお問い合わせ下さい！
      </p>
      <div class="my-4">
        <div class="flex justify-center items-center flex-wrap md:text-xl">
          <div class="flex md:justify-center align-right items-center">
            <img :src="image_src" alt="" class="h-12 w-12">
            <p class="font-semibold ">新車販売</p>
          </div>
          <div class="flex justify-center items-center">
            <img :src="image_src" alt="" class="h-12 w-12">
            <p class="font-semibold">中古車販売</p>
          </div>
          <div class="flex justify-center items-center">
            <img :src="image_src" alt="" class="h-12 w-12">
            <p class="font-semibold">新車販売</p>
          </div>
          <div class="flex justify-center items-center">
            <img :src="image_src" alt="" class="h-12 w-12">
            <p class="font-semibold">各種保険</p>
          </div>
        </div>
      </div>
    </div>
    <base-button name="トップに戻る" link="/" />
  </layout-wrapper>
</template>

<script>
export default {
  head() {
    return {
      title: 'コンセプト',
    }
  },
  data() {
    return {
      image_src: require("../../assets/img/brandlogo.png")
    }
  }
}
</script>
