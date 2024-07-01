<template>
    <div :class = "myDiv" @click="buy">
        <div>
            <h2> {{cardName}} </h2>
        </div>
        <div>
            <p> +{{cardOutput}} RCN/sec</p>
            <hr>
            <div>
                <p> {{cardLevel}} lvl </p>
                <p> {{cardPrice}} RCN </p>
             </div>
        </div>
    </div>
     </template>
<script setup>
    import {inject} from 'vue'
    defineProps({
    cardName:String,
    cardLevel:Number,
    cardPrice:Number,
    cardOutput:Number,
    })

    const raccoons_per_sec = inject('raccoons_per_sec')
    const raccoons = inject('raccoons')

    function buy(){
        if (raccoons >= cardPrice) {
            raccoons -= cardPrice;
            raccoons_per_sec += cardOutput;
        }
    }
     </script>

     <style scope>
     .myDiv{
    border: dashed black 1px;
    flex-basis: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
     }
    
     </style>