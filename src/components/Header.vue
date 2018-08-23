<template>
  <header>
    <img alt="Ipsum logo" src="../assets/logo.png">
    <div class="title">
      <h1>Ipsum Energy</h1>
      <p>Need an ipsum? We got it.</p>
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style scoped>

header {
  display: grid;
  grid-template-areas: "logo title title avatar";
  margin-bottom: 30px;
  box-shadow: 2px 2px 5px black;
  padding: 20px;
}

img {
  width: 150px;
  grid-area: logo;
  justify-self: center;
}

.title {
  grid-area: title;
}

h1 {
  font-size: 64px;
  color: #eb6624;
  text-shadow: 2px 2px #616161;
}

p {
  color: black;
}

</style>
