<template>
  <button class="button"
  @click="$emit('onCalculatorButtonClick', label)"
  :class="{double,triple,quatro,operation}">
  {{ label }}  
  </button>
</template>

<script>
export default {
  props: {
    label:{},
    operation:{type: Boolean},
    doble: {type: Boolean},
    triple: {type : Boolean},
    quatro: {type : Boolean},
  }
}
</script>

<style>
:root {
    --bg-button: #f0f0f0;
    --border-button: solid 1px #888;
}
.button {
    font-size: 1.4em;
    background-color: var(--bg-button);
    border: none;
    border-right: var(--border-button);
    border-bottom: var(--border-button);
    outline: none;
}
.button:active {
    background-color: #ccc;
}
.button.double {
    grid-column: span 2 ;
}
.button.triple {
    grid-column: span 3;
}

.button.quatro {
    grid-column: span 2;
}
.button.operation {
    background-color: #fa8231;
    color: #fff;
}
.button.operation:active {
    background-color: #7c421bcc;
}
</style>