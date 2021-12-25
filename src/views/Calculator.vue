<template>
    <section class="calculator">
    <div class="container mx-auto" style="width: 300px;">
        <h3 class="main-heading">Calculator</h3>
        <span class="input-section">
         <input v-model='expression' type="text" id="exp" class="form-control input-lg evaluate" autofocus="autofocus" onFocus="this.select()"/>
    </span>
        <div class="mx-lg-auto grid-btn" style="width: 400px;">
            <button class="btn-danger btn" @click="evaluate_('C')">C</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('%')">%</button>
            <button class="btn-outline-dark btn" @click="evaluate_('+/-')">+/-</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('/')">/</button><br>
            <button class="btn-outline-dark  btn" @click="evaluate_('9')">9</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('8')">8</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('7')">7</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('*')">X</button><br>
            <button class="btn-outline-dark  btn" @click="evaluate_('6')">6</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('5')">5</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('4')">4</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('-')">-</button><br>
            <button class="btn-outline-dark  btn" @click="evaluate_('3')">3</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('2')">2</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('1')">1</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('+')">+</button><br>
            <button class="btn-outline-dark  btn" @click="evaluate_('0')">0</button>
            <button class="btn-outline-dark  btn" @click="evaluate_('.')">.</button>
            <button class="btn-outline-info  btn" @click="evaluate_('<-')">back</button>
            <input type = "button"
            id = "btnSearch"
            class = "btn-success btn"
            value = "="
            @click="evaluate_('=')"/>
        </div>
    </div>
    <div class="mx-auto ending" style="width: 280px;">
        <h2 class="design">Designed By: </h2>
        <h1 class="designer">Zain-ul-Abdin</h1>
    </div>
    </section>
</template>

<script>
    export default {
    data() {
        return {
            expression: '',
            result: '',
            error: ''
        }
    },
    methods: {
        evaluate_: function (val) {
            if (val == 'C') {
                this.expression = '';
                // this.result = '';
            } else if (val == '%') {
                this.expression += '%';
            } else if (val == '+/-') {
                this.expression = eval(this.expression * -1);
                this.expression = '-' + this.expression;
            } else if (val == '<-') {
                this.expression = this.expression.substring(0, this.expression.length - 1);
            } else if (val == '=') {
                try {
                    this.expression = eval(this.expression);
                } catch (e) {
                    this.error = 'Invalid Expression';
                }
            } else {
                this.expression += val;
            }
        },        
    }
}
</script>

<style scoped>
.calculator {
  margin: auto;
  width: 50%;
  border: 0px solid green;
  padding: 10px;
    }

.container {
  margin: auto;
  width: 50%;
  border: 3px solid white;
  padding: 10px;
}
.btn {
        margin-right: 15px;
        margin-left: 12px;
        margin-bottom: 8px;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        font-size: 20px;
        font-weight: bold;
        border: none;
        background-color: #f1f1f1;
        color: #000;
        cursor: pointer;
        transition: all 0.5s ease-in-out;
    }

    .btn:hover {
        background-color: #000;
        color: #f1f1f1;
    }

input {
        /* margin: px; */
        margin-left: 7px;
        width: 280px;
        height: 40px;
        padding: 3px;
        border-radius: 30px;
        font-size: 14px;
        font-weight: bold;
        border: 1px solid grey;
        background-color: #f1f1f1;
        color: #000;
        cursor: pointer;
        transition: all 0.3s ease-in-out;
    
}
.grid-btn {
    padding: 5px;
}

.main-heading {
    text-align: center;
    font-size: 22px;
    text-decoration: bold;
}

.ending {
    text-align: center;
    margin-left: 25%;
}
</style>