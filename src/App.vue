<template>
    <div id="app">
        <Table_test v-bind:rows="rows"
                    v-on:add-row="addRow"
                    v-on:delete-row="deleteRow"
                    v-on:clear-table="clearTable"/>
    </div>
</template>

<script>
import Table_test from '@/components/Table-test'

export default {
    name: 'App',
    components: {
        Table_test
    },
    data() {
        return {
            rows: [
                {model: "Audi S4", power: 265},
                {model: "BMW M3", power: 321},
                {model: "Volvo S60R", power: 300},
                {model: "Alfa-Romeo 156GTA", power: 250},
            ]
        }
    },
    methods: {
        addRow(newRow) {
            this.rows.push(newRow)
        },
        deleteRow(){
            this.rows.pop()
        },
        clearTable(){
            this.rows = []
        }
    }
}
</script>

<style>

</style>
