<template>
    <tr>
        <td>{{row.model}}</td>
        <td>{{row.power}}</td>
    </tr>
</template>

<script>
export default {
    name: 'RowItem',
    props: {
        row: {
            type: Object,
            required: true
        },
    },
}
</script>