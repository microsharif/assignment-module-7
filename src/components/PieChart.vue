<script setup>
import { onBeforeUnmount, onMounted } from 'vue'

let chart = null

const dataset = [
  300, 50, 100
]

const data = {
  labels: [
    'Red',
    'Blue',
    'Yellow'
  ],
  datasets: [{
    label: 'My First Dataset',
    data: dataset,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)',
      'rgb(43, 105, 86)',
      'rgb(21, 21, 186)',
    ],
    hoverOffset: 4
  }]
}

const config = {
  type: 'pie',
  data: data,
}

onMounted(() => {
  const ctx = document.getElementById('chart')
  chart = new Chart(ctx, config)
})

onBeforeUnmount(() => {
    chart.destroy()
})

</script>

<template>
  <div class=" mx-auto w-[400px] h-[450px] bg-gray-400">
    <canvas id="chart">
    </canvas>
  </div>
</template>

<style scoped></style>