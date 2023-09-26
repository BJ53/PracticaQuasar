<template>
  <q-page padding>
    <div class="q-gutter-xs">
      <q-btn color="secondary">Uno</q-btn>
      <q-btn color="positive">Dos</q-btn>
      <q-btn color="negative">Tres</q-btn>
    </div>

    <h1 class="bg-green-3 text-center">Titulo</h1>

    <div
      class="row items-center bg-positive text-center text-white"
      style="height: 100px"
    >
      <p class="col">Lorem, ipsum dolor.</p>
      <p class="col">Lorem, ipsum dolor.</p>
      <p class="col">Lorem, ipsum dolor.</p>
    </div>

    <h6 class="text-accent">Texto</h6>
    <p class="shadow-9">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolores,
      blanditiis at odit assumenda illum obcaecati praesentium voluptates ad
      saepe rem corporis tempora totam nemo dolorem nam cumque beatae
      perferendis deleniti.
    </p>
    <h6 class="text-deep-orange-14">Texto</h6>
    <h6 class="text-negative">Texto</h6>
    <h6 class="text-green-7">Texto</h6>
    <p class="bg-dark text-white q-pa-xl">esto es un parrafo</p>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
