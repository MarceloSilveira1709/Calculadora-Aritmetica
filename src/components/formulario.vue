<script setup>
    const props = defineProps(["getNumber1", "getNumber2", "getOperador", "resultado"]);
</script>

<template>
    <form class="text-center">
    <div class="row">
        <div class="col">
        <input required type="number" placeholder="0" class="form-control mb-4" @keyup="props.getNumber1"/> 
        </div>
        <div class="col-md-2 mb-4 ">
        <select class="form-control " @change="props.getOperador">
            <option class="subtrair " value="subtrair">-</option>
            <option class="somar " selected value="somar">+</option>
            <option class="dividir " value="dividir">÷</option>
            <option class="multiplicar " value="multiplicar">x</option>
        </select>
        </div>
        <div class="col">
        <input required type="number" placeholder="0" class="form-control mb-4" @keyup="props.getNumber2"/>
        </div>
    </div>
    <div class="row">
        <div class="col">
        <h3 >Resultado</h3>
        </div>
    </div>
    <div class="row">
    <div class="col">
        <h2 >{{ props.resultado }}</h2>
        </div>
    </div>
    </form>
</template>

<style scoped>


</style>