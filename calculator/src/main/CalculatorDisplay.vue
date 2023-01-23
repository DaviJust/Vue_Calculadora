<template>
  <div class="calculator">
    <CalculatorDisplayBg></CalculatorDisplayBg>
    <CalculatorButton></CalculatorButton>
    <CalculatorButton></CalculatorButton>
    <CalculatorButton></CalculatorButton>
    <CalculatorButton></CalculatorButton>
    <CalculatorButton></CalculatorButton>
    <CalculatorButton></CalculatorButton>
  </div>
  
</template>

<script>
 import CalculatorButton from "../components/CalculatorButton.vue"
 import CalculatorDisplayBg from "../components/CalculatorDisplayBg.vue"
 export default {
    components: {CalculatorButton, CalculatorDisplayBg},

}

</script>

<style>

.calculator {
    height: 320px;
    width: 235px;
    border-radius: 5px;
    overflow: hidden;
    display: grid;
    grid-template-columns: repeat(4, 25%);
    grid-template-rows: 1fr 48px 48px 48px 48px 48px;
}
</style>