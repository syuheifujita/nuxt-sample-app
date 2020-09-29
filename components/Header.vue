<template>
    <header>
        <nav>
            <ul>
                <li><nuxt-link to="/">Home</nuxt-link></li>
                <li><nuxt-link to="/recipes">Recipes</nuxt-link></li>
                <li><nuxt-link to="/about">About</nuxt-link></li>
            </ul>
        </nav>
    </header>
</template>

<style scoped>
header {
    width: 100%;
    height: 50px;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
    background-color: blueviolet;
}

ul {
    list-style: none;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;    
}

li {
    margin: 10px 10px;
    font-weight: bold;
}

a {
    /* text style */
    text-decoration: none;
    color: white;
}
</style>
