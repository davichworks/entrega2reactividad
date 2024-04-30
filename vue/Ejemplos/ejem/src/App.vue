<template>
  <div>
    <h1>Ref Example</h1>
    <p>Contador: {{ refCount }}</p>
    <button @click="incrementRef">Incrementar Ref</button>

    <h1>Reactive Example</h1>
    <p>Nombre: {{ reactiveState.name }}</p>
    <p>Edad: {{ reactiveState.age }}</p>
    <input type="text" v-model="newName">
    <button @click="updateReactive">Actualizar Nombre</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
  setup() {
    // Ejemplo de Ref
    const refCount = ref(0);
    const newName = ref('');

    const incrementRef = () => {
      refCount.value++;
    };

    // Ejemplo de Reactive
    const reactiveState = reactive({
      name: 'John',
      age: 30
    });

    // Nuevo nombre a través de input
    

    const updateReactive = () => {
      if (newName.value.trim() !== '') {
        reactiveState.name = newName.value;
        newName.value = ''; // Limpiar el cuadro de texto después de la actualización
      }
    };

    return {
      refCount,
      incrementRef,
      reactiveState,
      newName,
      updateReactive
    };
  }
};
</script>

<style>
/* Estilos opcionales */
</style>
