<template>
<div class="loader">
  <div class="loader__hourglass"></div>
</div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
.loader {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 10%;
}
.loader__hourglass {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
}
.loader__hourglass:after {
  content: " ";
  display: block;
  border-radius: 50%;
  width: 0;
  height: 0;
  margin: 8px;
  box-sizing: border-box;
  border: 32px solid #34a8b8;
  border-color: #34a8b8 transparent #34a8b8 transparent;
  animation: loader__hourglass 1.2s infinite;
}
@keyframes loader__hourglass {
  0% {
    transform: rotate(0);
    animation-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
  50% {
    transform: rotate(900deg);
    animation-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
  }
  100% {
    transform: rotate(1800deg);
  }
}
</style>