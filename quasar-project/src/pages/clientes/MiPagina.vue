<template>
  <q-page padding>
    <h1>Formulario</h1>
    <q-form
      class="row q-col-gutter-md"
      @Sumbit.prevent="procesar_formulario"
      @reset="reset"
      ref="myform"
    >
      <div class="col-12 col-sm-3">
        <q-input
          standout="bg-teal text-white"
          v-model="producto"
          label="Producto"
          :rules="[
            (val) => (val && val.length > 0) || 'Por favor escriba algo',
          ]"
        />
      </div>
      <div class="col-12 col-sm-3">
        <q-select
          outlined
          v-model="seleccion"
          :options="opciones"
          label="Prioridad"
          :rules="[
            (val) => (val && val.length > 0) || 'Por favor inserte prioridad',
          ]"
        />
        <div class="col-3">
          <q-toggle v-model="terminos" label="Aceptar terminos" />
        </div>
      </div>
      <div class="col-12">
        <q-btn color="positive" label="Sumbit" type="submit" />
        <q-btn
          color="positive"
          label="Reset"
          outline
          class="q-ml-sm"
          :ripple="false"
          type="reset"
        />
      </div>
    </q-form>

    <pintar-datos :productos="productos" />
  </q-page>
</template>

<script>
import { ref } from "vue";
import { useQuasar } from "quasar";
import PintarDatos from "src/components/PintarDatos.vue";
export default {
  components: { PintarDatos },
  setup() {
    const $q = useQuasar();
    const myform = ref(null);
    const producto = ref(null);
    const seleccion = ref(null);
    const terminos = ref(false);
    const opciones = ["Max", "Inter", "Min"];
    const productos = ref([]);
    const procesar_formulario = () => {
      console.log("Clickeaste el formulario");
      if (terminos.value === false) {
        $q.notify({
          color: "red-5",
          textColor: "white",
          icon: "warning",
          message: "Acepte terminos",
        });
      } 
    };
    const reset = () => {
      producto.value = null;
      seleccion.value = null;
      terminos.value = false;
    };
    return {
      producto,
      seleccion,
      opciones,
      procesar_formulario,
      terminos,
      reset,
      myform,
      productos,
    };
  },
};
</script>
