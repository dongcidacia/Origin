<template>
    <div class="header">
        城市选择
        <router-link to='/'>
        <div>
            <div class="iconfont header-back">&#xe666;</div>
        </div>
        </router-link>
    </div>
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style scoped>
    .header{
        height: .86rem;
        line-height: .86rem;
        overflow:hidden;
        text-align: center;
        color:#fff;
        background-color: #00bcd4;
        font-size:  .32rem;
        position:relative;
    }
    .header-back{
        top:0;
        left: 0;
        width: .64rem;
        text-align: center;
        font-size:  .4rem;
        position: absolute;
        color:#fff;
    }
</style>