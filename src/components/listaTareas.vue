<template>
  <div id="lista">
      <h2> Crea una nueva tarea</h2>
      <label for="tarea" ><b>Tarea</b></label>
      <input :type="text" v-model="nuevasTareas" placeholder="Ingresa nueva tarea">
      <button @click="agregarTarea">Crear</button>
    <h4>Lista</h4>
    <ul >
      <li v-for="(value, $index) in tareas" :key="$index">{{ $index }}: {{ value }}</li> 
    </ul>
  </div>
</template>

<script>
export default {
    data: () => ({
      nuevasTareas: '',
      tareas: [],
  }),
     methods: {
      agregarTarea() {
        this.tareas.push( this.nuevasTareas )
        this.nuevasTareas = ''
      }
  }
}

</script>
<style scoped>
  ul{
    margin: 0 auto;
    text-align: left;
    padding-left: 15% ;
    width: 20%;
  }
</style>
