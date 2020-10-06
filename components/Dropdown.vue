<template>
    <div class="menu-item" @click="isHoverFlag = !isHoverFlag" @mouseover="isHoverFlag = true" @mouseleave="isHoverFlag = false">
        <a>{{ title }}</a>
        <svg viewBox="0 0 1030 638" width="10">
            <path d="M1017 68L541 626q-11 12-26 12t-26-12L13 68Q-3 49 6 24.5T39 0h952q24 0 33 24.5t-7 43.5z" 
            fill="#000"></path>
        </svg>
        <div class="sub-menu" v-if="isHoverFlag">
            <div v-for="(item, i) in items" :key="i" class="menu-item">
                <a :href="item.link">{{ item.title }}</a>
            </div>
        </div>
    </div>
</template>

<script>
import Vue from 'vue'

export default {
    name: 'dropdown',
    props: ['title', 'items'],
    data() {
        return {
            isHoverFlag: false,            
        }
    },
    methods: {
        click: function() {
            this.hoverflag = true
        }
    }
}
</script>

<style>
nav .menu-item svg {
    width: 10px;
    margin-left: 10px;
}

nav .menu-item .sub-menu {
    position: absolute;
    background-color: white;
    top: calc(100%);
    left: 0px;
    width: max-content;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.1);
}
</style>
