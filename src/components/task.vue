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
      <rowItem v-for="(row,index) in rowArray" :key="index" :index="index" :value="row" @plus="plus(index)" @minus="minus(index)" @delete="deleteRow($event)"></rowItem>
    </div>
  </div>
</template>
<script>
import rowItem from "./rowItem"
export default {
  components: {
    "rowItem": rowItem,
  },
  data(){
    return{
      rowArray: [0, 1, 3, 0, 1],
      divRow: null,
      removedArray: null,
    }
  },
  methods: {
    restore(){
    },
    plus(index){
      console.log("asda")
      this.rowArray = this.rowArray.splice(0,this.rowArray.length)
    },
    minus(index){
      console.log("asda")
      this.changedRow = this.rowArray
      if( this.changedRow[index] > 0){
        this.changedRow[index] -= 1
      }
      this.rowArray = this.changedRow
    },
    deleteRow(index){
      console.log("The index is  " + index)
      const rowArrayClone = [...this.rowArray];
      rowArrayClone.splice(index, 1);
      console.log('rowArrayClone', rowArrayClone);
      this.rowArray = rowArrayClone;
      console.log(this.rowArray)
    }
  },

}
</script>
