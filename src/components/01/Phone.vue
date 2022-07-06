<template>
  <div>
    <div class="tag">
      <span>中国大陆</span><input type="radio" name="1" /> <span>中国香港</span
      ><input type="radio" name="1" />
    </div>
    <slot>
      <van-field v-model="tel" type="tel" label="手机号" />
      <van-field
        v-model="sms"
        center
        clearable
        label="短信验证码"
        placeholder="请输入短信验证码"
      >
        <template #button>
          <van-button size="small" type="primary">发送验证码</van-button>
        </template>
      </van-field>
    </slot>
    <van-form @submit="onSubmit">
      <van-field
        v-model="username"
        name="用户名"
        label="用户名"
        placeholder="用户名"
        :rules="[{ required: true, message: '请填写用户名' }]"
      />
      <van-field
        v-model="password"
        type="password"
        name="密码"
        label="密码"
        placeholder="密码"
        :rules="[{ required: true, message: '请填写密码' }]"
      />
      <van-field
        v-model="password"
        type="password1"
        name="确认密码"
        label="确认密码"
        placeholder="确认密码"
        :rules="[{ required: true, message: '确认密码' }]"
      />
      <div style="margin: 16px">
        <van-button round block type="info" native-type="submit"
          >提交</van-button
        >
      </div>
    </van-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      password: "",
      username: "",
      sms: "",
      tel: "",
      onSubmit: "",
      password1: "",
    };
  },
  methods: {
    onClick(name, title) {
      Toast(name);
      console.log(name, title);
    },
  },
};
</script>

<style>
.tag {
  margin-left: 15px;
}
</style>
