<template>
  <div class="container">
    <div class="item d-flex">
        <p class="rounded-pill bg-primary text-white p-1 text-center">0</p>
      <h4 class="ms-1">Items</h4>
    </div>
    <div class="button-settings">
        <button class="btn-success btn">Refresh Number  <i class="fas fa-sync"></i></button>
        <button class="btn-primary btn ms-2" @click="restore">Restore <img src="../assets/restore.svg" width="20px" alt=""></button>
    </div>
    <div class="rows">
      <rowItem v-for="i in 5" :key="i" value="0" :id="i"></rowItem>
    </div>
  </div>
</template>
<script>
import rowItem from "./rowItem"
export default {
  data(){
    return{
      rows: null
    }
  },
  components: {
    "rowItem": rowItem,
  },
  methods: {
    restore(){
     this.rows = document.querySelector('.rows')
      console.log(this.rows)
      console.log(this.rows.children)
      if(this.rows.children.length == 0){
        console.log("empty")
      }
    }
  },

}
</script>
