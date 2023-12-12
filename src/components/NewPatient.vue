<template>
    <div>
      <h1 class="title">Registro de Paciente</h1>
      <form @submit.prevent="guardarPaciente">
        <div>
          <label for="nombre">Nombre:</label>
          <input type="text" id="nombre" v-model="paciente.nombre" required>
        </div>
        <div>
          <label for="fechaNacimiento">Fecha de Nacimiento:</label>
          <input type="date" id="fechaNacimiento" v-model="paciente.fechaNacimiento" required>
        </div>
        <div>
          <label>
            <input type="checkbox" v-model="paciente.primeraVisita"> ¿Es primera visita?
          </label>
        </div>
        <div>
          <label for="altura">Altura (cm):</label>
          <input type="number" id="altura" v-model.number="paciente.altura">
        </div>
        <div>
          <label for="peso">Peso (kg):</label>
          <input type="number" id="peso" v-model.number="paciente.peso">
        </div>
        <button type="submit">Guardar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        paciente: {
          nombre: '',
          fechaNacimiento: '',
          primeraVisita: false,
          altura: null,
          peso: null
        }
      };
    },
    methods: {
      guardarPaciente() {
        // Aquí puedes enviar los datos del paciente a tu backend o hacer lo que necesites con ellos
        console.log('Paciente:', this.paciente);
        // Puedes realizar una petición HTTP para guardar los datos en tu servidor
        // Ejemplo con axios: axios.post('/api/pacientes', this.paciente)
        // Tras guardar, podrías redirigir a otra página o realizar alguna otra acción
      }
    }
  };
  </script>
  
  <style>
  /* Estilos para el formulario de registro de pacientes */

/* Alineación del formulario y sus elementos */
form {
  max-width: 400px;
  margin: 0 auto;
}

.title {
  text-align: center; /* Centra el texto */
  margin-top: 0; /* Ajusta el margen superior si es necesario */
  /* Otros estilos si son necesarios */
}

/* Estilos para los campos del formulario */
label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

input[type="text"],
input[type="date"],
input[type="number"],
input[type="checkbox"] {
  width: 100%;
  padding: 8px;
  margin-bottom: 15px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

input[type="checkbox"] {
  width: auto;
  margin-bottom: 0;
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
  