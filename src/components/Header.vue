// Header.vue

<template>
    <div class="topbar">
        <p class="tagline">
            <img class="tagline__logo" src="../assets/nerp.svg" alt="Logo Nerp">
            <span class="tagline__title">LOU</span>
        </p>
        <!--
        <div id="nav">
            <router-link to="/">Home</router-link> •
            <router-link to="/games">Games</router-link>
        </div>
        -->
    </div>
</template>

<script>

</script>

<style>

.topbar {
    display: flex;
    justify-content: space-between;
    padding: 12px 24px;
    margin: 0 0 24px 0;
    color: hsl(0, 0%, 10%);
    background-color: #FFF;
}
.topbar a {
    color: hsl(0, 0%, 10%);
    text-decoration: none;
    margin: 0 10px;
}
.tagline {
    display: flex;
    align-items: center;
    margin: 0;
}
.tagline__logo {
    display: inline-block;
    width: 30px;
}
.tagline__title {
    position: relative;
    letter-spacing: 2px;
    font-weight: 300;
    font-size: 1.0rem;
    margin-left: 14px;
    padding-left: 8px;
    color: hsl(0, 0%, 10%);
}
.tagline__title::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    display: block;
    width: 6px;
    height: 1px;
    background-color: hsl(0, 0%, 10%);
    margin: auto;
    transform: translateX(-100%);
}

</style>