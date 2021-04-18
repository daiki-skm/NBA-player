<template>
    <header>
        <h1 class="pageTitle">NBA選手一覧</h1>
        <div class="search">
            <div class="result">
                検索結果<span class="count">{{count}}件</span>
            </div>
            <div class="condition">
                <div class="target">
                    <label>
                        <input type="checkbox" v-bind:checked="showAllStar" v-on:change="$emit('showAllStarChanged')">過去のAllStar
                    </label>
                </div>
                <div class="sort">
                    <label for="sort">並び替え</label>
                    <select id="sort" class="sorting" v-bind:value="sortOrder" v-on:change="$emit('sortOrderChanged',parseInt($event.target.value))">
                        <option value="1">標準</option>
                        <option value="2">身長が低い順</option>
                        <option value="3">体重が軽い順</option>
                    </select>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'PlayerHeader',
    props: ['count','showAllStar','sortOrder']
}
</script>

<style scoped>
.pageTitle{
    font-weight: normal;
    border-bottom: 2px solid;
}

.search{
    display: flex;
    justify-content: space-between;
}

.search .target{
    display: inline-block;
}

.search .target label{
    margin-right: 15px;
}

.search .sort{
    display: inline-block;
}
</style>