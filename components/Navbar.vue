<template>
    <nav>
        <div class="menu-item"><a href="/">Home</a></div>
        <Dropdown title="Content" :items="contents" />
        <div class="menu-item"><a href="/about">About</a></div>
    </nav>
</template>

<script>
import Dropdown from '@/components/Dropdown'

export default {
    name: 'navbar',
    components: [
        Dropdown
    ],
    data() {
        return {
            contents: [
                {
                    title: 'Drink',
                    link: '/recipes'
                },
                {
                    title: 'Other',
                    link: '/otherRecipes'
                }
            ]
        }
    }
}
</script>

<style>
nav {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
}

nav .menu-item {
    padding: 30px 40px;
    position: relative;
    text-align: center;
    border-bottom: 3px solid transparent;
    display: flex;
    transition: 0.4s;
}

nav .menu-item:active,
nav .menu-item:hover {
    background-color: whitesmoke;
    border-bottom-color: red;
}

nav .menu-item a {
    color: inherit;
    text-decoration: none;
    color: black;
}
</style>
