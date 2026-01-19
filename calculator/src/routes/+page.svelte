<script>
let display = '0';
let firstOperand = null;
let operator = null;
let waitingForSecondOperand = false;

function inputDigit(digit) {
    if (waitingForSecondOperand) {
        display = digit;
        waitingForSecondOperand = false;
    } else {
        display = display === '0' ? digit : display + digit;
    }
}

function inputOperator(nextOperator) {
    const inputValue = parseFloat(display);
    if (operator && waitingForSecondOperand) {
        operator = nextOperator;
        return;
    }

    if (firstOperand === null) {
        firstOperand = inputValue;
    } else if (operator) {
        const result = calculate(firstOperand, inputValue, operator);
        display = String(result);
        firstOperand = result;
    }
    waitingForSecondOperand = true;
    operator = nextOperator;
}

function calculate(firstOperand, secondOperand, operator) {
    switch (operator) {
        case '+': return firstOperand + secondOperand;
        case '-': return firstOperand - secondOperand;
        case '*': return firstOperand * secondOperand;
        case '/': return firstOperand / secondOperand;
        default: return secondOperand;
    }
}
</script>

<style>
button {
    font-size: 2em;
    margin: 0.2em;
}
</style>

<div>
    <div>{display}</div>
    <div>
        <button on:click={() => inputDigit('1')}>1</button>
        <button on:click={() => inputDigit('2')}>2</button>
        <button on:click={() => inputDigit('3')}>3</button>
        <button on:click={() => inputOperator('+')}>+</button>
    </div>
    <div>
        <button on:click={() => inputDigit('4')}>4</button>
        <button on:click={() => inputDigit('5')}>5</button>
        <button on:click={() => inputDigit('6')}>6</button>
        <button on:click={() => inputOperator('-')}>-</button>
    </div>
    <div>
        <button on:click={() => inputDigit('7')}>7</button>
        <button on:click={() => inputDigit('8')}>8</button>
        <button on:click={() => inputDigit('9')}>9</button>
        <button on:click={() => inputOperator('*')}>*</button>
    </div>
    <div>
        <button on:click={() => inputOperator('/')}>F7</button>
        <button on:click={() => inputDigit('0')}>0</button>
        <button on:click={() => inputOperator('=')}>=</button>
    </div>
</div>
