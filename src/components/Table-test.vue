<template>
    <div>
        <table border="1px solid black">
            <th>Model</th>
            <th>Power</th>
            <RowItem
                v-for="(row,i) of rows"
                v-bind:key="i"
                v-bind:row="row"/>
            <TotalRow v-bind:rows="rows"/>
            <tr>
                <td>
                    <input
                        type="text"
                        placeholder="Enter model:"
                        v-model="model"
                    >
                </td>
                <td>
                    <input
                        type="number"
                        placeholder="Enter power:"
                        v-model="power"
                    >
                </td>
            </tr>

        </table>
        <button v-on:click="$emit('clear-table')">Clear table</button>
        <button v-on:click="deleteRow()">Delete previous row</button>
        <button v-on:click="addRow()">Add row</button>
    </div>
</template>

<script>
import RowItem from "@/components/RowItem";
import TotalRow from "@/components/TotalRow";

export default {
    name: 'Table_test',
    data() {
        return {
            model:'',
            power:0
        }
    },
    components: {RowItem, TotalRow},
    props: ['rows'],
    methods:{
        addRow(){
            if (this.model.trim()) {
                const newRow= {model: this.model, power: this.power}
                this.$emit('add-row', newRow)
                this.model = ''
                this.power = 0
            }
        },
        deleteRow(){
            this.$emit('delete-row')
        }
    }
}
</script>