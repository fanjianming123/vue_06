<template>
  <div>
    <MyTable>
      <template v-slot:name='scope'>
          <input type="text" v-model="scope.row.name">
      </template>
       <template v-slot:age='scope'>  
          <input type="text" v-model="scope.row.age">
      </template>
       <template v-slot:url='scope'>
         <div v-if="scope.row.type == 0">
            <a :href="scope.row.headImgUrl">{{scope.row.headImgUrl}}</a>
          </div>  
          <div v-if="scope.row.type == 1">
            <img :src="scope.row.headImgUrl" alt="">
          </div>
          <div v-if="scope.row.type == 2">
            {{scope.row.headImgUrl}}
          </div>
      </template>
    </MyTable>
    
    <keepAlive></keepAlive>
   
  </div>
</template>

<script>
import MyTable from './components/MyTable.vue'
import keepAlive from './views/keep-alive.vue'
export default {
  components:{
    MyTable,
    keepAlive
  }
}
</script>

<style>

</style>