<template>
  <div class="button-section d-flex mt-2 justify-content-between">
    <h4 class="bg-primary text-white text-center fw-bold">{{ value }}</h4>
    <button @click="plus()" class="bg-secondary btn text-white fw-bold"><i class="fas fa-plus-circle"></i></button>
    <button @click="minus()" class="bg-info btn text-white fw-bold"><i class="fas fa-minus-circle"></i></button>
    <button @click="deleteFunction()" class="bg-danger btn text-white fw-bold"><i class="fas fa-trash"></i></button>
  </div>
</template>
<script>
export default {
  props: ["value","index"],

  methods:{
    plus(){
      this.$emit("plus",this.$props.index);
    },
    minus(){
      if(this.$props.value > 0) {
        this.$emit("minus",this.$props.index);
      }
    },
    deleteFunction() {
      this.$emit("delete",this.$props.index);
    }
  },
}
</script>
