<template>
  <div id="app">
    <h1>Calculadora</h1><CalculatorDisplay/>
  </div>
</template>

<script>
import CalculatorDisplay from "./main/CalculatorDisplay.vue"

export default {
  components:{CalculatorDisplay}
}
</script>

<style>

@font-face{
    font-family:"RobotoMono";
    src: url("./fonts/RobotoMono-Thin.ttf")
}

*{
    font-family: "RobotoMono", monospace;
    background-color:linear-gradient(#e66465, #9198e5);
}
body{
    margin:0;

}
#app{
    display:flex;
    flex-direction:column;
    height:100vh;
    justify-content: center;
    align-items: center;
    text-align: center;

    color: #fff;
    background: linear-gradient(#e66465, #9198e5);;
}

</style>