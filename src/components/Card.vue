<template>
  <div :class="[{'flip-card-show': show}, 'flip-card']">
    <div class="flip-card-inner">
      <div class="flip-card-front">
        Front
      </div>
      <div class="flip-card-back">
        Back
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['show']
}
</script>

<style lang="scss">
.flip-card {
  background-color: transparent;
  border: 1px solid #f1f1f1;
  perspective: 40em;
  width: 20em;
  height: 8em;;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card-show .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: gainsboro;
  color: black;
}

.flip-card-back {
  background-color: dodgerblue;
  color: white;
  transform: rotateY(180deg);
}
</style>
