<template>
    <div class="items">
        <div rows="999" class="row-items" >
            <div class="row-single-item" v-for="(item, index) in data.items" 
                :key="index"
                :style="item.style">
                <div style="height: 100%; width: 100%">
                    <img :src="item.img" class="item-image">
                    <div class="item-name">{{item.name}}</div>
                    <div v-if="item.caption" class="item-caption">{{item.caption}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script src="./items.js"></script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.items {
    display: block;
    background-image: url(../assets/shotaro-hamasaki-8FU_MZ2r0EQ-unsplash.jpg);
    background-size: cover;
}
.row-items {
    display: grid;
    grid-template-rows: repeat(999, 50px);
    grid-template-columns: repeat(8, minmax(0px, 1fr));
    max-width: 1400px;
    padding-left: 15px;
    padding-right: 15px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 15px;
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
    /* grid-row: 1 / span 2;
    grid-column: 5 / span 2; */
}
.item-image {
    max-width: 100%;
    max-height: 100%;
    height: 100%;
    object-fit: contain;
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
