<template>
  <div class="calculator">
    <CalculatorDisplayBg value="1000"/>
    <CalculatorButton label="AC" triple @onCalculatorButtonClick="clearMemory"/>
    <CalculatorButton label="/" operation @onCalculatorButtonClick="setOperation"/>
    <CalculatorButton label="7" @onCalculatorButtonClick="addDigit"/>
    <CalculatorButton label="8" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="9" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="*" @onCalculatorButtonClick="setOperation" operation/>
    <CalculatorButton label="4" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="5" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="6" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="-" @onCalculatorButtonClick="setOperation" operation/>
    <CalculatorButton label="1" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="2" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="3" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="+" @onCalculatorButtonClick="setOperation" operation/>
    <CalculatorButton label="0" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="=" @onCalculatorButtonClick="setOperation" triple operation/>
  </div>
  
</template>

<script>
 import CalculatorButton from "../components/CalculatorButton.vue"
 import CalculatorDisplayBg from "../components/CalculatorDisplayBg.vue"
 export default {
    components: {CalculatorButton, CalculatorDisplayBg},
    methods: {
      clearMemory(){
        console.log('Limpar memória')
      },
      setOperation(operation){
        console.log('Operação' + operation)
      },
      addDigit(n){
        console.log("Digito" + n)
      }
    }
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