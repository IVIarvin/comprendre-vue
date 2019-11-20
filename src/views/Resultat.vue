<template>
  <div id="resultat">
      <hello></hello>
    <h1>Mes résultats</h1>
    <form>
      <label>Votre nom:</label>
      <br />
      <input type="text" name="firstname" />
      <br />
      <label>Votre prénom:</label>
      <br />
      <input type="text" name="lastname" v-model.trim="prenom" />
      <br />
      <label>Votre âge:</label>
      <br />
      <br />
      <input name="age" v-model.number="age" type="number" v-on:change="StopTeenager" />
      <br />
        <br />
      <label>Votre salaire:</label>
      <br>
      <input name="salaire" v-model.number="salaire" type="number" v-on:change="add100">
      <br />
      <label>Votre profession:</label>
      <br />
      <select name="prefessions" id="profession">
        <option value v-for="(el,i) in professions" v-bind:key="i">{{el}}</option>
      </select>
      <br />
      <button>Enregistrer</button>
    </form>
    <h1>{{age}}</h1>
  </div>
</template>

<script>
import HelloWorld from '@components/HelloWorld';
export default {
  methods: {
    StopTeenager() {
      if (this.age < 18) {
        this.age = 18;
      }
    },
  },
  components:{
      "hello":HelloWorld
  },
  data() {
    return {
      prenom: "",
      nom:"",
      salaire:null,
      profession:"",
      professions:["Informaticien","Docteur","AFP","Garde du corps","Protecteur de la planète Terre"],
      age: 18,
      message: "Hello Vue.js!"
    };
  }
};
</script>

<style>
</style>