<script>
export default {
  name: 'MyCard',
  props: {
    name: { default: '', type: String },
    person: { default: () => {}, type: Object }
  },
  setup(props, { emit }) {
    const childClick = () => {
      emit('addLike')
    }
    return { props, childClick }
  }
}
</script>
<template>
  <div class="article-container">
    <div class="title">
      Vue3 Yes！
    </div>
    <div class="subtitle">author:{{ props.person.name }} | posted:2020年5月20日</div>
    <div class="content">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ipsam aliquam, itaque deserunt
      voluptate reiciendis nobis voluptatibus labore autem, ex consectetur beatae quibusdam ab
      accusantium amet voluptatem quisquam? Aliquam, excepturi earum.
    </div>
    <div class="information">
      Like:{{ props.person.like }}
      <button @click="childClick">Like?</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.article-container {
  display: flex;
  left: 50%;
  top: 30%;
  width: 60vw;
  position: relative;
  transform: translate(-50%, -30%);
  flex-direction: column;
  background-color: beige;
  align-items: center;
  .title {
    font-size: 50px;
  }
  .subtitle {
    font-size: 16px;
    opacity: 0.6;
    padding-bottom: 10px;
  }
  .content {
    width: 40vw;
    text-indent: 1cm;
    text-align: start;
    padding-bottom: 10px;
  }
}
</style>
