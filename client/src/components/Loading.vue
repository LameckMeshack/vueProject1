<template>
  <h1><span class="loader"></span></h1>
</template>
<script>
export default {
  name: "LoadComponent",
};
</script>
<style scoped>
.loader {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  display: inline-block;
  border-top: 4px solid #fff;
  border-right: 4px solid transparent;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
  margin: 200px 400px;
}
.loader::after {
  content: "";
  box-sizing: border-box;
  position: absolute;
  left: 0;
  top: 0;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border-left: 4px solid #ff3d00;
  border-bottom: 4px solid transparent;
  animation: rotation 0.5s linear infinite reverse;
}
@keyframes rotation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
