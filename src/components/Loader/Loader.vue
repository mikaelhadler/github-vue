<template>
  <div class="lds-dual-ring"></div>
</template>

<script>
export default {
  name: 'Loading',
};
</script>

<style lang="css" scoped>
.lds-dual-ring {
  position: relative;
  top: 3em;
  left: 48%;
}
.lds-dual-ring:after {
  content: " ";
  display: block;
  width: 46px;
  height: 46px;
  margin: 1px;
  border-radius: 50%;
  border: 5px solid #000;
  border-color: #000 transparent #000 transparent;
  animation: lds-dual-ring 1.2s linear infinite;
}
@keyframes lds-dual-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
