<script setup>
import {ref} from 'vue'

const estado = ref(false)
const notas = ['nota1','nota2','nota3','nota4','nota5','nota6']


function showActivar (data){
    if(data === 1){

        estado.value= false

    }else{

        estado.value = true
    }
}

</script>

<!-- <template>

        
        <div class="h-screen w-full flex items-center">
            
            
            <div class=" w-2/4 mx-auto grid grid-cols-3 p-2 gap-3 relative " :class="{'bg-green-400' :estado}">

                <div class="flex items-center absolute top-[-35px] right-5 space-x-5">
                    <div class="cursor-pointer" @click="showActivar(1)">+</div>
                    <div class="cursor-pointer" @click="showActivar(0)">-</div>
                </div>
                
                
                <div v-for="(nota,i) in notas" :key="i" class="bg-slate-300 w-full p-1 h-52 " :class="{'bg-red-400' :estado}">
                    
                    <div class="bg-white w-full h-32 " :class="{'bg-blue-200' : estados}"></div>
                    <p class=" px-3 ">{{ nota }}</p>
                </div>
            </div>
        </div>
    

</template> -->

<template>
    <div class="w-full h-screen bg-slate-200 flex items-center">
        <div class="mx-auto w-2/4 border grid gap-3 p-5 relative" 
            :class="estado ? 'grid-rows-6' : 'grid-cols-3'">
            <div class="flex space-x-8 w-6 h-6 absolute top-[-50px] right-6">
                <div class="cursor-pointer" @click="showActivar(1)">+</div>
                <div class="cursor-pointer" @click="showActivar(0)">-</div>
            </div>
            <div v-for="(nota, i) in notas" :key="i" class="bg-[#caddd7] w-full p-1"
                :class="estado ? 'flex h-auto col-span-3' : 'h-52'">
                <div class="w-full h-32 bg-white" :class="estado ? 'w-5 h-5 mr-3' : 'h-32'"></div>
                <p>{{ nota }}</p>
            </div>
        </div>
    </div>
</template>