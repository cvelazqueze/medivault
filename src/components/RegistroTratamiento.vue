<template>
    <div>
      <h1 class="title">Registro de Tratamiento</h1>
      <div class="patient-info">
        <p>Nombre del Paciente: {{ paciente.nombre }}</p>
        <!-- Otras informaciones del paciente si son necesarias -->
      </div>
      <form @submit.prevent="guardarTratamiento">
        <div>
          <label for="medicamento">Nombre del Medicamento:</label>
          <input type="text" id="medicamento" v-model="tratamiento.medicamento" required>
        </div>
        <div>
          <label for="tipo">Tipo:</label>
          <select id="tipo" v-model="tratamiento.tipo" required>
            <option value="tableta">Tableta</option>
            <option value="capsula">Cápsula</option>
            <option value="inyeccion">Inyección</option>
            <!-- Otras opciones de tipos de tratamiento -->
          </select>
        </div>
        <div>
          <label for="dosis">Dosis:</label>
          <input type="text" id="dosis" v-model="tratamiento.dosis" required>
        </div>
        <div>
          <label for="frecuencia">Frecuencia:</label>
          <input type="text" id="frecuencia" v-model="tratamiento.frecuencia" required>
        </div>
        <button type="submit">Guardar Tratamiento</button>
      </form>
    </div>
  </template>
  
  <script>
  // Importa las funciones necesarias o define los props si es necesario
  
  export default {
    data() {
      return {
        paciente: {
          nombre: 'Nombre del Paciente', // Aquí puedes obtener el nombre del paciente registrado
          // Otras informaciones del paciente si son necesarias
        },
        tratamiento: {
          medicamento: '',
          tipo: 'tableta',
          dosis: '',
          frecuencia: ''
        }
      };
    },
    methods: {
      guardarTratamiento() {
        // Lógica para guardar el tratamiento, por ejemplo, enviar los datos al backend
        console.log('Tratamiento:', this.tratamiento);
        // Puedes realizar una petición HTTP para guardar los datos en tu servidor
        // Ejemplo con axios: axios.post('/api/tratamientos', this.tratamiento)
        // Tras guardar, podrías redirigir a otra página o realizar alguna otra acción
      }
    }
  };
  </script>
  
  <style scoped>
  /* Estilos CSS para el formulario de registro de tratamiento, puedes ajustar según sea necesario */
  .title {
    text-align: center;
  }
  
  .patient-info {
    margin-bottom: 20px;
  }
  
  input[type="text"],
  select {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
  
  button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  