<template>
  <div>
    <button @click="comName = 'Phone'">手机注册</button>
    <button @click="comName = 'Email'">邮箱注册</button>
    <div style="border: 1px solid #EDEDED">
    <keep-alive>
        <component :is="comName"></component>
    </keep-alive>
    </div>
  </div>
</template>

<script>
import Email from '../components/Email.vue'
import Phone from '../components/Phone.vue'
export default {
  data() {
    return {
        comName:"Phone"
    }
  },
      components: {
        Email,
        Phone
    }
}
</script>

<style></style>
