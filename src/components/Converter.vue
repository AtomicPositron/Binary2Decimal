<template>
   <div class="container d-flex align-items-center flex-column my-5">
    <div class="input-group w-100 gap-10">
        
        <input type="text" v-model="value" placeholder="binary" class="form-control w-25 input mx-2">
        <div class="input-group-append">
            <button v-on:click="converter(value)" class="btn btn-success">Convert</button>
        </div>
    </div>
    <br>
    <p class="alert alert-success w-50 h-0 display-3 text-center font-weight-bolder">{{ finalValue }}</p>
   </div>
</template>

<script lang="ts" setup>
import { ref } from  'vue'

let value  = ref<string>('')
let finalValue = ref<number>(0)

function converter(binary: string){
    finalValue.value = 0
    let lenOfBinary = binary.length
    let baseValue: number = 2
    let binValue = []
    for (let i = 0; i < binary.length; i++) {

        if(lenOfBinary == -1){
            break;
        }else{
            let binaryFloat: number = +binary[i]
            if(binaryFloat == 0 || binaryFloat == 1){
                binValue.push(binCalculator(binaryFloat, lenOfBinary-1, baseValue))

            }

        lenOfBinary--
        console.log(lenOfBinary)
        }
    }
    console.log(binValue)


    for (let i = 0; i < binValue.length; i++) {
        finalValue.value += binValue[i]
        
    }


}
function binCalculator(x: number, n: number, b: number){
    console.log(x, n, b)
    let a = x * Math.pow(b, n)
    console.log(a)
    return(a)
}

</script>
