<template>
    <div>
        <h1> {{ title }} </h1>
        <ul class = "list-group">
 <!--
 add v-bind: or simply : to html attributes and make it equal to a specific variable
 the variable can come from data function or it can come from imported data
     -->
            <li v-for = "country in data.countries"
                :key = "country.id"
                class = "list-group-item">
                <span :id="country.id"
                      :title = "country.details">
                {{ country.id }} - {{ country.name }}
                </span>
            </li>
        </ul>
    </div>
</template>

<script>
    import data from '../data/data'
    export default {
        name: "VacationPicker",
        data() {
            return {
                data, //the same name used for the import line
                title: 'My next vacation'
            }
        }
    }
</script>

<style scoped>

</style>