<template>
  <div>
    <el-form-item label="选择所在地区" style="margin-left: 20px">
      <el-radio-group v-model="ruleForm.resource" style="margin-top: 0px">
        <el-radio label="中国大陆"></el-radio
        ><el-radio label="中国香港"></el-radio>
      </el-radio-group>
    </el-form-item>

    <el-form-item label="手机号码">
      <el-input v-model="ruleForm.name">
        <slot :row="phoneNum"></slot>
      </el-input>
    </el-form-item>
    <div class="send">
      <el-input
        v-model="input"
        placeholder="输入验证码"
        style="margin: 0 20px"
      ></el-input>
      <el-button type="primary" icon="el-icon-search">发送验证码</el-button>
    </div>
    <el-form-item label="登录密码" prop="name">
      <el-input v-model="ruleForm.name1"> </el-input>
      <el-input
        v-model="ruleForm.name2"
        style="margin-top: 10px"
        placeholder="再次输入登录密码"
      >
      </el-input>
    </el-form-item>
    <el-form-item label="邀请码（选填）" prop="name">
      <el-input v-model="ruleForm.name3" placeholder="输入客户经理邀请码">
      </el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="submitForm('ruleForm')"
        >立即注册</el-button
      >
      <el-button @click="resetForm('ruleForm')">重置</el-button>
    </el-form-item>
  </div>
</template>
<script>
export default {
  data() {
    return {
      ruleForm: {
        name: '',
        name1: '',
        name2: '',
        name3: '',
      },
      input: '',
      phoneNum: 15008092720,
      rules: {
        name: [
          { required: true, message: '请输入活动名称', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' },
        ],
      },
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!');
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    },
  },
};
</script>
<style scoped>
.send {
  display: flex;
  margin-bottom: 10px;
}
</style>
