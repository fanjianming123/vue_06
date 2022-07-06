<template>
  <div>
    <table border="1">
      <thead>
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>头像</th>
        </tr>
      </thead>
      <thead>
        <tr v-for="item in arr" :key="item.id">
          <td>
            <slot name="xuha" :xuhao="item"></slot>
          </td>
          <td>
            <slot name="ming" :mingz="item"></slot>
          </td>
          <td>
            <slot name="nian" :nianl="item"></slot>
          </td>
          <td>
            <slot name="img" :imga="item"></slot>
          </td>
        </tr>
      </thead>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    arr: Array,
  },
}
</script>

<style></style>
