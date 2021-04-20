<template>
    <label>Alas</label>
    <input type="number" @keyup="hitung" name="alas" v-model="state.alas"/>
  <br />
  <label>Tinggi</label>
  <input type="number" @keyup="hitung" name="tinggi" v-model="state.tinggi"/>

</template>
<script>
import {reactive ,watch } from "vue";
export default {
    setup(props,context) {
        const state = reactive({
            alas:0,
            tinggi:0,
            
        });
        watch(state,()=>{
            context.emit('form',state);
        })
        return{
            state
        }
    },
}
</script>