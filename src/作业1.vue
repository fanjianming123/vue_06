<template>
  <div class="demo">
    <h2>
      <span :class="{ active: isTrue }" @click="ChangePhone">手机注册</span> |
      <span :class="{ active: !isTrue }" @click="ChangeEmail">邮箱注册</span>
    </h2>
    <keep-alive>
      <component :is="comName">可自定义</component>
    </keep-alive>
  </div>
</template>
<script>
import PhoneRegister from './components/PhoneRegister.vue'
import EmailRegister from './components/EmailRegister.vue'
export default {
  data() {
    return {
      isTrue: true,
      comName: 'PhoneRegister',
    }
  },
  components: {
    EmailRegister,
    PhoneRegister,
  },
  mounted() {},
  computed: {},
  methods: {
    ChangePhone() {
      this.isTrue = true
      this.comName = 'PhoneRegister'
    },
    ChangeEmail() {
      this.isTrue = false
      this.comName = 'EmailRegister'
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
