<template>
    <div>
        <router-link tag="div" 
        to="/" 
        class="header-abs" 
        v-show="showAbs">
            <div class="iconfont header-abs-back">&#xe666;</div>
        </router-link>
        <router-link to="/"
            tag="div"
            class="header-fixed" 
            v-show="!showAbs" 
            :style="opacityStyle" >
            <div class="iconfont header-fixed-back">&#xe666;</div>
            景点详情
        </router-link>
    </div>
</template>

<script>
export default {
    name: 'DetailHeader',
    data () {
        return {
            showAbs: true,
            opacityStyle: {
                opacity: 0
            }
        }
    },
    mounted () {
        window.addEventListener('scroll', this.handleScroll)
    },
    destroyed () { //全局事件解绑
        window.removeEventListener('scroll', this.handleScroll)
    },
    methods: {
        handleScroll () {
            const top = document.documentElement.scrollTop || document.body.scrollTop || window.pageYOffset
            if (top > 60) {
                let opacity = top / 140
                opacity = opacity > 1?1:opacity
                this.opacityStyle = { opacity }
                this.showAbs = false
            } else {
                this.showAbs = true
            }
        }
    }
}
</script>

<style scoped>
.header-fixed{
    height: .86rem;
    line-height: .86rem;
    overflow:hidden;
    text-align: center;
    color:#fff;
    background-color: #00bcd4;
    font-size:  .32rem;
    position:relative;
}
.header-abs{
    position: absolute;
    left: .2rem;
    top: .2rem;
    width: .8rem;
    height: .8rem;
    line-height: .8rem;
    text-align: center;
    border-radius: .4rem;
    background:rgba(0,0,0,.8);
}
.header-abs-back{
    color: #fff;
    font-size: .4rem;
}
.header-fixed{
        height: .86rem;
        line-height: .86rem;
        text-align: center;
        color:#fff;
        background-color: #00bcd4;
        font-size:  .32rem;
        position:fixed;
        top: 0;
        right: 0;
        left: 0;
        z-index: 2;
    }
.header-fixed-back{
    top:0;
    left: 0;
    width: .64rem;
    text-align: center;
    font-size:  .4rem;
    position: absolute;
    color:#fff;
}
</style>