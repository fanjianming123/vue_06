<template>
  <div>
    <div class="title">
      <h3 style="margin-right: 20px" class="blue" @click="comName = 'phoneZhu'">
        手机注册
      </h3>
      <h3 @click="comName = 'emailZhu'">邮箱注册</h3>
    </div>
    <el-form
      :model="ruleForm"
      :rules="rules"
      ref="ruleForm"
      label-width="100px"
      class="demo-ruleForm"
    >
      <keep-alive>
        <component :is="comName" @click="comName = 'phoneZhu'" v-slot="scope">
          <h4>{{scope.row.phoneNum}}</h4>
        </component>
      </keep-alive>
    </el-form>
  </div>
</template>
<script>
import phoneZhu from './phoneZhu.vue';
import emailZhu from './emailZhu.vue';
export default {
  data() {
    return {
      ruleForm:{

      },
      rules:{

      },
      comName: 'phoneZhu',
      isShow: true,
    };
  },
  components: {
    phoneZhu,
    emailZhu,
  },
};
</script>
<style scoped>
.title {
  display: flex;
  margin-left: 30px;
}
.send {
  display: flex;
  margin-bottom: 10px;
}
.blue {
  color: blue;
}
</style>
