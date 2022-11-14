<template>
    <div class="search-bar ps-2 my-3">
        <select name="category" id="">
            <option value="volvo">Select category</option>
        </select>
    </div>
</template>

<script>
    export default {
        name: 'SearchbarComponent'
    }
</script>

<style lang="scss" scoped>
.search-bar select { padding: 5px; font-size: 13px; border-radius: 5px;}
</style>