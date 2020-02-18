<template>
    <div class="altimeter">
        <div class="{ scrollPosition < 4800 ? 'altimeter hidden' , 'altimeter' }">

            <h1 class="reading"> {{ scrollPosition ? scrollPosition : null }} meters high</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Altimeter',
    data () {
        return {
            scrollPosition: 6,
        }
    },
    methods: {
    updateScroll () {
    // Any code to be executed when the window is scrolled
        window.scroll();
        this.scrollPosition = window.scrollY;
        // eslint-disable-next-line no-console
        console.log("scrolling");
    }
    },
    created () {
        window.addEventListener('scroll', this.updateScroll);
    },
    destroyed () {
        window.removeEventListener('scroll', this.updateScroll);
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.altimeter {
    /* position: sticky; */
    position: fixed;
    bottom: 18%;
    width: 100%;
    left: 50%;
    text-align: center;
    z-index: 3;
    opacity: 1;
    transform: translateX(-50%);
    transition: opacity 0.3s ease-in-out 0s;
    border-bottom: 1px dashed rgba(255, 255, 255, 0.2);
}

.reading {
    text-align: center;
}
.hidden {
    opacity: 0;
}
.visible {
    opacity: 1
}
    /* position: sticky;
    bottom: 18%;
    width: 100%;
    text-align: center;
    font-weight: bold;
    padding-bottom: 10px;
    font-size: 28px;
    transform: translateY(-50%);
    color: white;
    z-index: 3;
    font-family: Roboto, sans-serif;
    opacity: 1;
    border-bottom: 1px dashed rgba(255, 255, 255, 0.2);
    transition: opacity 0.3s ease-in-out 0s; */

</style>
