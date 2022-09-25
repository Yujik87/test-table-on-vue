<template>
    <tr>
        <td>Total: {{ totalCount }}</td>
        <td>Average power: {{ averagePower }}</td>
    </tr>
</template>

<script>
export default {
    name: 'TotalRow',
    props: ['rows'],
    computed: {
        totalCount() {
            return this.rows.length
        },
        averagePower() {
            return ((this.rows.reduce((acc, el) => (acc + Number(el.power)), 0) / this.totalCount).toFixed(1))
        }
    }
}
</script>