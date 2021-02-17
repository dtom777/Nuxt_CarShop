<template>
  <layout-wrapper>
    <layout-visual title=Contact message="お問い合わせ" :height="53" visual="visual-chat" />
      <div class="text-white mx-4 pt-4 md:text-xl text-lg">
        <div class="md:text-2xl text-xl font-bold text-center mb-4 text-yellow-500">メールでのお問い合わせ</div>
        <hr>
        <form class="my-6">
          <div class="mb-4">
            <label for="name">お名前：</label>
            <input type="text" id="name" class="border text-black" v-model="form.name.contents">
          </div>
          <div class="mb-4">
            <label>性別：</label>
            <label for="man" class="ml-4">男</label>
            <input type="radio" id="man" name="gender" value="男" v-model="form.gender.contents">
            <label for="woman">女</label>
            <input type="radio" id="woman" name="gender" value="女" v-model="form.gender.contents">
          </div>
          <div class="mb-4">
            <label for="mail">E-mail：</label>
            <input type="text" id="mail" class="border text-black" size="30" v-model="form.email.contents">
          </div>
          <div class="mb-4">
            <label for="contact" class="align-top">お問合せ内容詳細：</label>
            <textarea id="contact" cols="35" rows="3" class="border text-black" v-model="form.message.contents"></textarea>
          </div>
          <button class="px-4 py-2 mx-auto block rounded-md bg-yellow-500 text-black" type="button" @click="sendMail">Send</button>
        </form>
      </div>
    <base-button name="トップに戻る" link="/" />
  </layout-wrapper>
</template>

<script>
import firebase from '~/plugins/firebase.js'

export default {
  data() {
    return {
      form: {
        name: { contents: '' },
        gender: { contents: '' },
        email: { contents: '' },
        message: { contents: '' },
      }
    }
  },
  methods: {
    sendMail() {
      const form = this.form
      const sendMail = firebase.functions().httpsCallable('sendMail')
      sendMail({ form })
        .then((response) => {
          alert(response)
          this.$router.push("/contact/")
        })
        .catch((error) => {
          alert(error)
        })
    }
  },
}

</script>
