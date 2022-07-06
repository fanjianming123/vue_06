<template>
  <el-form
    :model="ruleForm"
    :rules="rules"
    ref="ruleForm"
    label-width="100px"
    class="demo-ruleForm"
  >

    <el-form-item label="选择地区" prop="Area" label-position='top'>
      <el-radio-group v-model="ruleForm.Area" >
        <el-radio label="中国大陆"></el-radio>
        <el-radio label="中国香港"></el-radio>
      </el-radio-group>
    </el-form-item>

    <el-form-item label="邮箱地址" prop="name">
      <el-input v-model="ruleForm.name"></el-input>
      <el-input v-model="ruleForm.checkNum" style="width:60%;margin-top:10px;float:left;"></el-input>
      <el-button type="primary" style="width:35%;float:right;margin-top:10px;">发送验证码</el-button>
    </el-form-item>
    <!-- 插槽 -->
    <slot>
<!-- 默认组件 -->
 <el-form-item label="密码" prop="pass">
 <el-input type="password" v-model="ruleForm.pass" autocomplete="off"></el-input>
  </el-form-item>
  <el-form-item label="确认密码" prop="checkPass">
    <el-input type="password" v-model="ruleForm.checkPass" autocomplete="off"></el-input>
  </el-form-item>

    </slot>
  
    <el-form-item>
      <el-button type="primary" @click="submitForm('ruleForm')"
        >立即注册</el-button
      >
      <el-button @click="resetForm('ruleForm')">重置</el-button>
    </el-form-item>
  </el-form>
</template>
<script>
export default {
  data() {
     let validatePass = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请输入密码'));
        } else {
          if (this.ruleForm.checkPass !== '') {
            this.$refs.ruleForm.validateField('checkPass');
          }
          callback();
        }
      };
      let validatePass2 = (rule, value, callback) => {
        if (value === '') {
          callback(new Error('请再次输入密码'));
        } else if (value !== this.ruleForm.pass) {
          callback(new Error('两次输入密码不一致!'));
        } else {
          callback();
        }
      }
    return {
      ruleForm: {
        name: '',
        Area: '中国大陆',
        checkNum:'',
        pass:'',
        checkPass:''

      },
      rules: {
        name: [
          { required: true, message: '请输入邮箱地址', trigger: 'blur' },
          { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' },
        ],
        Area: [
          { required: true, message: '请选择地区', trigger: 'change' },
        ],
          checkNum: [
          { required: true, message: '请输入验证码', trigger: 'change',type:'number' },
        ],
         pass: [
            {  required: true,validator: validatePass, trigger: 'blur' }
          ],
          checkPass: [
            {  required: true,validator: validatePass2, trigger: 'blur' }
          ],
      },
    }
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
      }
  },
}
</script>
