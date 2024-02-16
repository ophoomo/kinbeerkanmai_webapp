<script setup lang="ts">
  import Button from 'primevue/button';
import { ref } from 'vue';
  const count = ref(0);
  const listMessage = ref([
    {
      title: "ไปกินเบียร์กันไหม",
      yes: "ไปปปกันนนน",
      no: "ดูก่อนน"
    },
    {
      title: "เดี๋ยวเลี้ยง",
      yes: "ไปดิ",
      no: "ไม่เอาๆ กินแล้วได้ไรวะ"
    },
    {
      title: "ก็ได้เสมอออ ไงไอสัสส",
      yes: "อ้าวววไปดิ",
      no: "ไม่ๆ"
    },
    {
      title: "ไปเถอะ น้าาาา",
      yes: "ไปก็ได้ๆ",
      no: "ไม่ไป"
    }
  ]);

  const changeState = () => {
    if(count.value < listMessage.value.length - 1) count.value++;
  }

  const scaleButton = () => {
    return 1 + (count.value/5)
  }

  const GoKinBeer = () => {
    alert("ไปดิ จะรออยู่ไม");
  }

</script>

<template>
  <div class="flex gap-3 flex-col">
    <h1 class="text-6xl mb-10 font-bold">{{ listMessage[count].title }}</h1>
    <Button @click="GoKinBeer" :style="{transform: `scale(${scaleButton()},${scaleButton()})`}">{{ listMessage[count].yes }}</Button>
    <Button @click="changeState" severity="danger">{{ listMessage[count].no }}</Button>
  </div>
</template>
