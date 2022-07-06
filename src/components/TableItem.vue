<template>
  <tr>
    <td><slot name="ItemId"   :row='item.id'></slot></td>
    <td><slot name="ItemName" :row='item.name'>{{item.name}}</slot></td>
    <td><slot name="ItemAge"  :row='item.age'>{{item.age}}</slot></td>
    <td><slot name="ItemUrl"  :row='item.headImgUrl'></slot></td>
  </tr>
</template>
<script>
export default {
  data() {
    return {}
  },
  props:{
   item:{
    type:Object,
    default:()=>({})
   }
  },
  components: {},
  mounted() {},
  computed: {},
  methods: {},
}
</script>
<style scoped></style>
