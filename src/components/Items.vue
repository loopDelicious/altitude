<template>
    <div class="items">
        <div rows="99" class="row-items" >
            <div class="row-single-item" v-for="(item, index) in data.items" 
                :key="index"
                :style="'grid-area: ' + (data.maxHeight - item.positionRow) + ' / ' + item.positionColumn + ' / span ' + item.rowSpan + ' / span ' + item.columnSpan + ';'">
                <div style="height: 100%; width: 100%">
                    <img :src="item.img" class="item-image">
                    <div class="item-name">{{item.name}}</div>
                    <div v-if="item.caption" class="item-caption">{{item.caption}}</div>
                </div>
            </div>
        </div>
        <Altimeter />
    </div>
</template>

<script>

import Altimeter from './Altimeter.vue'
import data from '../data/items.json'

export default {
  name: 'Items',
  components: {
    Altimeter
  },
  data () {
    return {
        data: data,
    }
  },
  methods: {
    handleScroll () {
    // Any code to be executed when the window is scrolled
        window.scroll();
        
        // eslint-disable-next-line no-console
        console.log("scrolling");
    },
    created () {
        window.addEventListener('scroll', this.handleScroll);
    },
    destroyed () {
        window.removeEventListener('scroll', this.handleScroll);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.items {
    display: block;
    background-color: silver;
    /* background-image: url(../assets/tom-barrett-hgGplX3PFBg-unsplash.jpg); */
    /* background-size: cover; */
    /* position: relative; */
}
.row-items {
    display: grid;
    grid-template-rows: repeat(99, 50px);
    grid-template-columns: repeat(8, minmax(0px, 1fr));
    max-width: 1400px;
    padding-left: 15px;
    padding-right: 15px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 15px;
    padding-bottom: 30px;
    position: relative;
    z-index: 2;
    gap: 0px;
}
.row-single-item {
    width: 100%;
    text-align: center;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    -webkit-box-pack: center;
    justify-content: center;
    /* position: absolute; */
    /* grid-row: 1 / span 2;
    grid-column: 5 / span 2; */
}
.item-image {
    max-width: 100%;
    max-height: 100%;
    height: 100%;
    object-fit: contain;
}
.item-name {
    text-transform: uppercase;
}
.item-caption {
    font-size: 16px;
    margin-top: 5px;
    color: rgb(247, 241, 227);
    font-weight: lighter;
    opacity: 0.9;
    text-transform: uppercase;
    font-family: Oswald, sans-serif;
}
</style>
