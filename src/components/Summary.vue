<template>
    <h3>Luas dari segitiga yang memiliki alas {{alas}} dan tinggi {{tinggi}} adalah {{luas}}</h3>
</template>

<script>
export default {
   props:{
       alas:Number,
       tinggi:Number,
       luas:Number
   }
}
</script>