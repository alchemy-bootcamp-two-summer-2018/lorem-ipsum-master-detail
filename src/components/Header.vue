<template>
    <header>
        <img class="logo" src="images/ipsumlogo.png" alt="logo" height="100">
        <h1> Ipsum Creator </h1>
    </header>
</template>

<script>
export default {
};
</script>

<style scoped>

.selected {
    background: pink;
}

li {
    background: grey;
    list-style:none;
    border: solid 1px black;
}

header {
    top: 0;
    left: 0;
    width: 100vw;

}
.logo {
    display: center; 
    width: 20%;

}
h1 {
    text-align: center;
}
</style>
