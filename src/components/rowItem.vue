<template>
  <div :id="`button-section-` + this.$props.id" class="button-section d-flex mt-2 justify-content-between">
    <h4 class="bg-primary text-white text-center fw-bold">{{ count }}</h4>
    <button @click="plus($event)" class="bg-secondary btn text-white fw-bold"><i class="fas fa-plus-circle"></i></button>
    <button @click="minus($event)" class="bg-info btn text-white fw-bold"><i class="fas fa-minus-circle"></i></button>
    <button @click="deleteRow($event)" class="bg-danger btn text-white fw-bold"><i class="fas fa-trash"></i></button>
  </div>
</template>
<script>
export default {
  props: ["value","id"],
  data(){
    return{
      count: parseInt(this.$props.value)
    }
  },
  methods:{
  plus(event){
    this.count += 1;
  },
  minus(event){
    if(this.count > 0){
      this.count -= 1;
  }
},
  deleteRow(event) {
    event.currentTarget.parentElement.remove()
  }
}

}
</script>
