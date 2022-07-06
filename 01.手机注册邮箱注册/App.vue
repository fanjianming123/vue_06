<template>
  <div class="demo">
    <h2>
      <span :class="{ active: !isShow }" @click="ChangePhone">手机注册</span>
      <span :class="{ active: isShow }" @click="ChangeEmail">邮箱注册</span>
    </h2>
    <div>
      <keep-alive>
      <component :is="isName"></component>
      </keep-alive>
    </div>
  </div>
</template>
<script>
import Phone from './components/PhoneRegister.vue'
import EmailBase from './components/EmailBase.vue'
export default {
  data() {
    return {
      isShow: false,
      isName: 'EmailBase',
    }
  },
  components: {
    Phone,
    EmailBase,
  },
  mounted() {},
  computed: {},
  methods: {
    ChangePhone() {
      this.isName = 'EmailBase'
      this.isShow = !this.isShow
    },
    ChangeEmail() {
      this.isName = 'Phone'
      this.isShow = !this.isShow
    },
  },
}
</script>
<style scoped>
.demo {
  position: absolute;
  width: 500px;
  left: calc(50% - 250px);
  top: 10%;
  padding: 10px;
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(6px);
  border-radius: 5px;
}
h2 {
  cursor: pointer;
}
.active {
  color: #409eff;
  font-size: 30px;
}
</style>
