<script setup lang="ts">
import ChatBox from '../components/ChatBox.vue';
import QuizComponent from '../components/QuizComponent.vue';

const load = (e: Event) => {
  const img = e.target as HTMLImageElement
  img.style.width = img.offsetWidth * 0.2 + 'px'
}

const drag = (e: TouchEvent) => {
  e.preventDefault()
  const img = e.target as HTMLImageElement
  img.style.left = e.touches[0].clientX - img.offsetWidth / 2 + 'px'
  img.style.top = e.touches[0].clientY - img.offsetHeight / 2 + 'px'
}
</script>

<template>
  <div class="background">
    <div class="header">
      <RouterLink to="/map"><button>返回</button></RouterLink>
      <RouterLink to="/calligraphy"><button>书法</button></RouterLink>
      <QuizComponent pageContext="请生成关于满族面塑艺术的多样化问题，可涉及：1)历史渊源(面塑艺术的起源与发展); 2)制作材料(面粉、糯米粉、甘油等原料特点); 3)工艺技法(捏、搓、压、揉、掀等手法及工具使用); 4)题材类型(花鸟鱼虫、人物动物等常见题材); 5)文化内涵(面塑作品蕴含的象征意义与民俗文化); 6)地域特色(不同地区面塑风格差异); 7)现代传承与创新(传统工艺的保护与发展)。问题可以是基础知识型、工艺技术型、文化分析型、历史探究型或趣味民俗型，让学习者能够全面了解面塑这一独特的民间艺术形式及其在满族文化中的地位与价值。" />
    </div>
    <ChatBox class="box"
      text="面塑以面粉、糯米粉、甘油或澄面等为主要原料，通过手工和专用塑形工具，经过捏、搓、压、揉、掀等手法，用小竹刀点、切、刻、划、塑成栩栩如生的艺术形象，如花、鸟、鱼、虫、景物、器物、人物、动物等。俗称面花、礼馍、花糕或捏面人。这一传统艺术在中国历史上有着悠久的渊源，汉代即有文字记载，而宜宾面塑更是在清末民初兴起，至今已有百余年历史。面塑艺术通过色彩搭配和巧妙的手法，展现了生动、灵活、富有创意的艺术形象，为中华文化传统的独特表达方式之一。" />
    <div class="workspace">
      <img v-for="n in 14" :alt="`part${n}`" :src="`/assets/craft/${n}.webp`" @load="load" @touchmove="drag" />
    </div>
    <div class="final">
      <div>拖动拼装面塑</div>
      <img src="/assets/craft/final.webp" @load="load" />
    </div>
  </div>
</template>

<style scoped>
.workspace {
  margin: 20px;
}

.workspace img {
  position: fixed;
}

.final {
  position: absolute;
  right: 0;
  bottom: 0;
  font-size: 0.8rem;
  display: inline-flex;
  flex-direction: column;
  align-items: center;
}

.header {
  display: flex;
  align-items: center;
  padding: 10px;
}

.quiz {
  margin: 0 10px;
  flex: 1;
}
</style>