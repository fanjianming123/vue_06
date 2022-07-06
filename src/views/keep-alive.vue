<template>
  <div>
    <button @click="comName = 'Phone'">手机注册</button>
    <button @click="comName = 'Email11'">邮箱注册</button>

    <div style="border: 1px solid pink">
      <keep-alive>
        <component :is="comName"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import Phone from '../components/01/Phone.vue'
import Email11 from '../components/01/Email111.vue'
export default {
  data() {
    return {
      comName: 'Phone',
    };
  },
  components: {
    Phone,
    Email11,
  },
};
</script>

<style></style>
