<template>
  <div>
    <Phone :arr="list">
      <template v-slot:xuha="scope">
        {{ scope.xuhao.id }}
      </template>
      <template v-slot:ming="scopeaa">
        {{ scopeaa.mingz.name }}
      </template>
      <template v-slot:nian="scopebb">
        {{ scopebb.nianl.age }}
      </template>
      <template v-slot:img="scopecc">
        <img
          v-if="scopecc.imga.type == 1"
          :src="scopecc.imga.headImgUrl"
          alt=""
          style="width: 50px"
        />
        <a
          v-else-if="scopecc.imga.type == 0"
          :href="scopecc.imga.headImgUrl"
        >{{scopecc.imga.headImgUrl}}</a>
        <p v-else>{{ scopecc.imga.headImgUrl }}</p>
      </template>
    </Phone>
  </div>
</template>
<script>
import Phone from './components/PhoneRegister.vue'
export default {
  data() {
    return {
      list: [
        {
          id: 100,
          name: '小传同学',
          age: 18,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210303/603f2d2153241.jpg',
          type: 0, // 0 显示成a标签
        },
        {
          id: 101,
          name: '小黑同学',
          age: 25,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210304/6040b101a18ef.jpg',
          type: 1, // 1 显示成图片
        },
        {
          id: 102,
          name: '智慧同学',
          age: 21,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210302/603e0142e535f.jpg',
          type: 1, // 1 显示成图片
        },
        {
          id: 103,
          name: '智慧同学',
          age: 21,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210302/603e0142e535f.jpg',
          type: 2, // 2 显示成文本
        },
        {
          id: 101,
          name: '小黑同学',
          age: 25,
          headImgUrl:
            'http://yun.itheima.com/Upload/./Images/20210304/6040b101a18ef.jpg',
          type: 1, // 1 显示成图片
        },
      ],
    }
  },
  components: {
    Phone,
  },
}
</script>
<style scoped></style>
