<template>
  <div class="card">
    <div class="card-image">
      <img :src="image" alt="" class="card-image" />
    </div>
    <div class="card-text">
      {{ name }}
    </div>
  </div>
</template>

<script>
export default {
  props: ["name", "image"],
};
</script>

<style >
.card {
  display: grid;
  grid-template-rows: 210px 210px;
  grid-template-areas: "image" "text";
  border-radius: 18px;
  background: white;
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.9);
  font-family: roboto;
  text-align: center;
}

.card-image {
  grid-area: image;
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
  background-size: cover;
  padding: 10px;
}
.card-image img {
    width: 80%;
    height: 100%;
}
.card-text {
  display: grid;
  grid-area: text;
  width: 100%;
  align-items: center;
  font-size: 28px;
}
</style>