<script>
import { reactive, ref, onMounted } from 'vue'
import MyCard from '@/components/MyCard'
export default {
  components: {
    MyCard
  },
  setup() {
    const person = reactive({
      name: 'cad',
      age: '18',
      like: 0
    })

    const card = ref(person)

    const addLike = () => {
      card.value.like++
    }

    onMounted(() => {
      console.log('life hooks onMounted!')
    })

    return { person, card, addLike }
  }
}
</script>
<template>
  <div class="about" style="height:900px">
    <h1>Hello {{ person.name }}</h1>
    <h1>Like:{{ card.like }}</h1>
    <button @click="addLike">click me please</button>
    <MyCard :person="person" @addLike="addLike" />
  </div>
</template>
