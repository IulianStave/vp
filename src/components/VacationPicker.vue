
<template>
    <!--
        HTML attributes and events binding
    v-bind: Binding to the html attributes id, title
    'v-on:click = ' or '@click' Binding to click event inside button
    :key is a vue attribute that sets a key
    shorthand notations :id,  @click
    -->
    <div>
        <h1> {{ appTitle }} </h1>
   
        <h3> Clicks counter: {{ counter }}</h3>
        <button v-on:click="increment" class ="btn btn-success">+</button> &nbsp;
        <button v-on:click="counter--" class ="btn btn-warning">-</button>
        <br/>
        <br/>
        <button @click="counter=0" class="btn btn-info"> Reset </button>
        <br/>
        <br/>
        <button class="btn btn-info">No action</button>
        <ul class = "list-group">
            <li v-for = "country in data2List.countries"
                v-bind:key = "country.id"
                class = "list-group-item"
                @click="showCountry(country)"
                >
                <span :id="country.id"
                      :title = "country.details">
                {{ country.id }} -
                {{ country.name }}<br/>
            <!--    
                {{ country.details }}
            -->
                </span>
            </li>
        </ul>
    
    </div>
</template>

<script>
    import data2List from '../data/data'
    // what will be exported into App.vue
    export default {
        name: "VacationPicker",
        data() {
            return {
                data2List, //the same name used for the import line
                //title of the app can be declared and exported
                appTitle: 'Next vacation - 2019',
                // declare the counter
                counter: 0
            }
        },
        // define methods called at events like click
        methods: {
            increment : function(){
                //the function is called by click event +
                this.counter++;
            },
            decrement(){
                this.counter--;
            },
            showCountry(country){
                alert("you clicked on:"+country.name);
            }
        }
    }
</script>

<style scoped>

</style>