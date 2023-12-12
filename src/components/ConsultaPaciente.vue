<template>
    <div>
      <h1 class="title">Registro de Consulta</h1>
      <div class="patient-info">
        <p>Nombre del Paciente: {{ paciente.nombre }}</p>
        <!-- Otras informaciones del paciente si son necesarias -->
      </div>
      <form @submit.prevent="guardarConsulta">
        <div>
          <label for="razonConsulta">Razón de la Consulta:</label>
          <textarea id="razonConsulta" v-model="consulta.razon" required></textarea>
        </div>
        <div>
          <label for="fechaConsulta">Fecha de Consulta:</label>
          <input type="date" id="fechaConsulta" v-model="consulta.fecha" required>
        </div>
        <button type="submit">Guardar Consulta</button>
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
        consulta: {
          razon: '',
          fecha: ''
        }
      };
    },
    methods: {
      guardarConsulta() {
        // Lógica para guardar la consulta, por ejemplo, enviar los datos al backend
        console.log('Consulta:', this.consulta);
        // Puedes realizar una petición HTTP para guardar los datos en tu servidor
        // Ejemplo con axios: axios.post('/api/consultas', this.consulta)
        // Tras guardar, podrías redirigir a otra página o realizar alguna otra acción
      }
    }
  };
  </script>
  
  <style scoped>
  /* Estilos CSS para el formulario de consulta, puedes reutilizar y ajustar según sea necesario */
  .title {
    text-align: center;
  }
  
  .patient-info {
    margin-bottom: 20px;
  }
  
  textarea,
  input[type="date"] {
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