<template>
    <div :class = "myDiv" @click="$emit('cardTapl')">
        <div>
            <h2> {{cardName}} </h2>
        </div>
        <div>
            <p> +{{cardOutput}} RCN/clck</p>
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

    const raccoons_per_clck = inject('raccoons_per_clck')
    const raccoons = inject('raccoons')

    function buy(){
        if (raccoons >= cardPrice) {
            raccoons -= cardPrice;
            raccoons_per_clck += cardOutput;
        }
    }
</script>

<style >
.myDiv{
    border: dashed black 1px;
    flex-basis: 120px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
     }
    
 </style>