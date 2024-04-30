<script>
	// Define una variable reactiva para el contador
	let contador = 0;
  
	// Función para incrementar el contador
	function incrementar() {
	  contador += 1;
	}
  
	// Define un objeto reactiva para la persona
	let persona = {
	  nombre: '',
	  edad: 0,
	  ciudad: ''
	};
  
	// Función para manejar el envío del formulario
	function handleSubmit(event) {
	  event.preventDefault(); // Evitar el comportamiento predeterminado de recargar la página
	  console.log(persona); // Mostrar el objeto persona en la consola
	}
  </script>
  
  <main>
	<!-- Primer ejemplo de reactividad: Contador -->
	<section>
	  <h2>Ejemplo de Reactividad: Contador</h2>
	  <div>
		<h3>Contador: {contador}</h3>
		<button on:click={incrementar}>Incrementar</button>
	  </div>
	</section>
  
	<!-- Segundo ejemplo de reactividad: Formulario de Registro -->
	<section>
	  <h2>Ejemplo de Reactividad: Formulario de Registro</h2>
	  <form on:submit={handleSubmit}>
		<label for="nombre">Nombre:</label>
		<input type="text" id="nombre" bind:value={persona.nombre}>
  
		<label for="edad">Edad:</label>
		<input type="number" id="edad" bind:value={persona.edad}>
  
		<label for="ciudad">Ciudad:</label>
		<input type="text" id="ciudad" bind:value={persona.ciudad}>
  
		<button type="submit">Enviar</button>
	  </form>
  
	  <p>Información ingresada:</p>
	  <ul>
		<li>Nombre: {persona.nombre}</li>
		<li>Edad: {persona.edad}</li>
		<li>Ciudad: {persona.ciudad}</li>
	  </ul>
	</section>
  </main>
  
  <style>
	main {
	  text-align: center;
	  margin-top: 50px;
	}
  
	section {
	  margin-bottom: 50px;
	}
  
	button {
	  margin-top: 10px;
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
  
	input {
	  padding: 5px;
	  border-radius: 3px;
	  border: 1px solid #ccc;
	}
  
	ul {
	  list-style: none;
	  padding: 0;
	}
  
	li {
	  margin-bottom: 5px;
	}
  </style>
  