<template>
  <div class="container">
    <div class="item d-flex">
        <p class="rounded-pill bg-primary text-white p-1 text-center">0</p>
      <h4 class="ms-1">Items</h4>
    </div>
    <div class="button-settings">
        <button class="btn-success btn">Refresh Number</button>
        <button class="btn-primary btn ms-2">Restore</button>
    </div>
    <div class="button-section" v-for="i in 5">
        <div class="mt-2">
          <p class="bg-primary d-inline-block text-white text-center fw-bold">0</p>
          <button class="bg-secondary btn text-white fw-bold"><i class="fas fa-plus-circle"></i></button>
          <button class="bg-info btn text-white fw-bold"><i class="fas fa-minus-circle"></i></button>
          <button class="bg-danger btn text-white fw-bold"><i class="fas fa-trash"></i></button>

        </div>
    </div>
  </div>
</template>
