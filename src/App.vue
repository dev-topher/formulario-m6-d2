<template>
  <div id="app">
    <div class="container">
      <div class="form-container">
        <h1>Formulario</h1>
        <form>
          <div class="form-group">
            <label for="title">Título:</label>
            <input type="text" id="title" v-model="title" />
          </div>
          <div class="divider"></div>

          <div class="form-group">
            <label for="emoji">Emoji:</label>
            <select id="emoji" v-model="emoji">
              <option value="😊">😊</option>
              <option value="😢">😢</option>
              <option value="😡">😡</option>
            </select>
          </div>
          <div class="divider"></div>

          <div class="form-group">
            <label>Apreciación:</label>
            <div class="radio-group">
              <div>
                <input type="radio" id="regular" value="Regular" v-model="appreciation" />
                <label for="regular">Regular</label>
              </div>
              <div>
                <input type="radio" id="good" value="Bien" v-model="appreciation" />
                <label for="good">Bien</label>
              </div>
              <div>
                <input type="radio" id="very-good" value="Muy bien" v-model="appreciation" />
                <label for="very-good">Muy bien</label>
              </div>
              <div>
                <input type="radio" id="amazing" value="Increíble" v-model="appreciation" />
                <label for="amazing">Increíble</label>
              </div>
            </div>
          </div>
          <div class="divider"></div>

          <div class="form-group">
            <label>Competencias aprendidas:</label>
            <div class="checkbox-group">
              <div class="column">
                <div>
                  <input type="checkbox" id="competence1" value="Morfología de un componente" v-model="competences" />
                  <label for="competence1">Morfología de un componente</label>
                </div>
                <div>
                  <input type="checkbox" id="competence2" value="One-Way y Two-Way data binding" v-model="competences" />
                  <label for="competence2">One-Way y Two-Way data binding</label>
                </div>
                <div>
                  <input type="checkbox" id="competence3" value="El patrón de diseño MVVM" v-model="competences" />
                  <label for="competence3">El patrón de diseño MVVM</label>
                </div>
              </div>
              <div class="column">
                <div>
                  <input type="checkbox" id="competence4" value="Estado" v-model="competences" />
                  <label for="competence4">Estado</label>
                </div>
                <div>
                  <input type="checkbox" id="competence5" value="Directivas" v-model="competences" />
                  <label for="competence5">Directivas</label>
                </div>
              </div>
            </div>
          </div>
          <div class="divider"></div>

          <div class="form-group">
            <label for="opinion">Opinión:</label>
            <textarea id="opinion" v-model="opinion"></textarea>
          </div>
        </form>
      </div>

      <div class="output-container">
        <p>{{ emoji }}</p>
        <p>{{ title }}</p>
        <p>Y me parece {{ appreciation }}</p>
        <p>{{ competences.join(', ') }}</p>
        <p>Mi opinión hasta ahora del framework es:</p>
        <p>{{ opinion }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      emoji: '',
      appreciation: '',
      competences: [],
      opinion: ''
    }
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f8f9fa;
  margin: 0;
  padding: 0;
}

.container {
  display: flex;
  justify-content: space-around;
  padding: 20px;
  max-width: 1200px;
  margin: 0 auto;
}

.form-container, .output-container {
  width: 45%;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form-container {
  background-color: #212529;
  color: #ffffff;
}

h1, h2 {
  color: #343a40;
}

.form-container h1 {
  color: #ffffff;
}

.form-group {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}

label {
  display: inline-block;
  margin-right: 10px;
  font-weight: bold;
  width: auto; /* Ajusta esto según sea necesario */
}

input[type="text"], select, textarea {
  width: calc(100% - 160px);
  padding: 10px;
  border: 1px solid #ced4da;
  border-radius: 5px;
  box-sizing: border-box;
  background-color: #343a40;
  color: #ffffff;
}

select {
  width: auto;
  padding: 5px;
}

input[type="radio"], input[type="checkbox"] {
  width: auto;
  margin-right: 5px;
}

textarea {
  height: 50px;
  font-family: 'Courier New', Courier, monospace;
}

.radio-group, .checkbox-group {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
}

.checkbox-group .column {
  display: flex;
  flex-direction: column;
  margin-right: 20px;
}

.divider {
  width: 100%; /* Ajuste para alinear con el label */
  height: 2px;
  background: linear-gradient(to right, #999, #000, #999);
  margin: 10px 0;
  border-radius: 2px;
  margin-left: 1px; /* Alinea con el inicio de los labels */
}

.output-container {
  background-color: #ffffff;
  color: #212529;
  border: 1px solid #ced4da;
  display: flex;
  flex-direction: column;
  align-items: center; /* Centra los elementos horizontalmente */
  justify-content: center; /* Centra los elementos verticalmente */
}

.output-container p {
  margin: 10px 0;
}

strong {
  color: #495057;
}
</style>
