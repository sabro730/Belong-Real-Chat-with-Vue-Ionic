<template>
  <div class="card-container" :class="[card.type, mask ? 'card-mask' : '']">
    <div class="card"></div>
  </div>
</template>

<script lang="ts" setup>
interface IProps {
  card: {
    type: string
  }
  mask: boolean
}

const props = defineProps<IProps>()
</script>

<style scoped>
.card-container.card-mask {
  height: 240px;
  overflow: hidden;
}

.card-container .card {
  width: 100%;
}

.card-container.generic .card,
.card-container.pass .card {
  height: 560px;
  border-radius: 0px;
  background-position: center top;
}

.card-container.apple-cash .card,
.card-container.debit .card {
  height: 240px;
  border-radius: 10px;
  background-position: center center;
}

.card-container .card {
  background-size: contain;
  background-repeat: no-repeat;
}

.card-container.debit .card {
  background-image: url('../assets/card.png');
}

.card-container.apple-cash .card {
  background-image: url('../assets/cash.png');
}

.card-container.pass .card {
  background-image: url('../assets/pass.png');
}

.card-container.generic .card {
  background-image: url('../assets/generic.png');
}
</style>
