<template>
    <div class="item">
        <figure class="image">
            <img v-bind:src="player.image" alt="">
            <figcaption v-html="player.name"></figcaption>
        </figure>
        <div class="detail">
            <div class="height"><span>{{player.height}}</span>cm</div>
            <div class="weight"><span>{{player.weight}}</span>kg</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Player',
    props: ['player']
}
</script>

<style scoped>
.item{
    flex: 0 1 250px;
    margin-bottom: 50px;
}

.item .image{
    position: relative;
    text-align: center;
}

.item .image img{
    width: 100%;
    height: auto;
}


.item .detail{
    text-align: center;
}

.item .height .weight{
    display: inline-block;
}

.item .height .weight span{
    font-size: 180%;
}

.item{
    display: inline-block;
    background: #f7cd12;
    color: #000;
}

.item{
    background: #bf0000;
    color: #fff;
}
</style>