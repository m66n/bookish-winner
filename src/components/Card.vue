<template>
  <div :class="[{'flip-card-show': show}, 'flip-card']">
    <div class="flip-card-inner">
      <div class="flip-card-front">
        <p class="is-size-2">{{current[0]}}</p>
      </div>
      <div class="flip-card-back">
        <p class="is-size-2">{{current[1]}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['show', 'current']
}
</script>

<style lang="scss">
.flip-card {
  background-color: transparent;
  border: 1px solid hsl(0, 0%, 93%);
  perspective: 40em;
  width: 20em;
  height: 8em;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0s;
  transform-style: preserve-3d;
}

.flip-card-show .flip-card-inner {
  transition: transform 0.8s;
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.flip-card-front {
  background-color: hsl(0, 0%, 86%);
  color: hsl(0, 0%, 29%);
}

.flip-card-back {
  background-color: hsl(171, 100%, 41%);
  color: hsl(0, 0%, 29%);
  transform: rotateY(180deg);
}
</style>
