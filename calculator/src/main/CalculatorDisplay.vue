<template>
  <div class="calculator">
    <CalculatorDisplayBg :value="displayValue" />
    <CalculatorButton label="AC" triple @onCalculatorButtonClick="clearMemory" />
    <CalculatorButton label="/" operation @onCalculatorButtonClick="setOperation" />
    <CalculatorButton label="7" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="8" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="9" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="*" @onCalculatorButtonClick="setOperation" operation />
    <CalculatorButton label="4" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="5" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="6" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="-" @onCalculatorButtonClick="setOperation" operation />
    <CalculatorButton label="1" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="2" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="3" @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="+" @onCalculatorButtonClick="setOperation" operation />
    <CalculatorButton label="0" quatro @onCalculatorButtonClick="addDigit"/>
    <CalculatorButton label="." @onCalculatorButtonClick="addDigit" />
    <CalculatorButton label="=" @onCalculatorButtonClick="setOperation"  operation />
  </div>

</template>

<script>
import CalculatorButton from "../components/CalculatorButton.vue"
import CalculatorDisplayBg from "../components/CalculatorDisplayBg.vue"
export default {
    data: function() {
        return {
            displayValue: "0",
            clearDisplay: false,
            operation: null,
            values: [0, 0],
            current: 0
        }
    },
    components: { CalculatorButton, CalculatorDisplayBg },
    methods: {
        clearMemory() {
            Object.assign(this.$data, this.$options.data())
        },
        setOperation(operation) {
            if (this.current === 0) {
                this.operation = operation
                this.current = 1
                this.clearDisplay = true
            } else {
                const equals = operation === "="
                const currentOperation = this.operation
                try {
                    this.values[0] = eval(
                        `${this.values[0]} ${currentOperation} ${this.values[1]}`
                        
                    )
                } catch (e) {
                    this.$emit('onError', e)
                }
                this.values[1] = 0
                this.displayValue = this.values[0]
                this.operation = equals ? null : operation
                this.current = equals ? 0 : 1
                this.clearDisplay = !equals
            }
        },
        addDigit(n) {
            if (n === "." && this.displayValue.includes(".")) {
                return
            }
            const clearDisplay = this.displayValue === "0"
                || this.clearDisplay
            const currentValue = clearDisplay ? "" : this.displayValue
            const displayValue = currentValue + n
            this.displayValue = displayValue
            this.clearDisplay = false
            
            this.values[this.current] = displayValue
            

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