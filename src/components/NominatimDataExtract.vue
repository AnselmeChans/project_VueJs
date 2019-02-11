<template>
    <table>
        <tr>
            <th> Lagitude </th>
            <th> Longitude </th>
        </tr>
        <tr v-for="coord in coordata" :key="coord.place_id">
            <td>{{coord.lat}}</td>
            <td>{{coord.lon}}</td>
        </tr>
    </table>
</template>

<script>
export default {
    name: "nominatimResult",
    props: ["coordata"]
}
</script>


<style lang="stylus" scoped>
    table
        height: 400px;
        width: 300px
</style>

