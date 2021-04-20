<template>
  <h2>Luas Segitiga - Composition API</h2>
 
  <!-- <input type="number" @keyup="hitung" name="alas" v-model="alas"/>
  <br />
  <label>Tinggi</label>
  <input type="number" @keyup="hitung" name="tinggi" v-model="tinggi"/> -->

  
  <!-- <label>Alas</label>
  <input type="number" @keyup="hitung" name="alas" v-model="alas"/>
  <br />
  <label>Tinggi</label>
  <input type="number" @keyup="hitung" name="tinggi" v-model="tinggi"/>
  <h3>Luas = {{luas}}</h3>-->

  <Form @form="hitungLuas($event)"/>
    <h3>Luas = {{luas}}</h3>
  <Summary :alas="alas" :luas="luas" :tinggi="tinggi"/> 
</template>

<script>
//import {  reactive } from "vue";
import { ref } from "vue";
import Summary from './components/Summary.vue';
import Form from "./components/Form.vue"
export default {
  name: "App",
  components:{
    Summary,
    Form
  },
  setup() {
    const alas = ref(0);
    const tinggi = ref(0);
    const luas = ref(0);
    // const luas = computed(()=>parseFloat(alas.value) * parseFloat(tinggi.value) * 0.5);

    function hitungLuas(event){
      luas.value = parseFloat(event.alas) * parseFloat(event.tinggi) * 0.5;
      tinggi.value = event.tinggi;
      alas.value = event.alas
    }
    // function hitung(){
    //   luas.value = parseFloat(alas.value) * parseFloat(tinggi.value) * 0.5
    // }
    // const state = reactive({ 
    //   alas:0,
    //   tinggi :0,
    //   luas:0,
    // });
    // watch(luas,(newValue,oldValue)=>{

    //   console.log("luasSebelumnya " + oldValue);
      
    //   console.log("luasSekarang " + newValue);

    // })
    return{
      alas,
      tinggi,
      luas,
      hitungLuas
      // hitung
      // state 
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
