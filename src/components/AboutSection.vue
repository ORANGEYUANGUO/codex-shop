<template>
  <section class="about" id="about">
    <div class="about-inner">
      <div class="about-img">🍯</div>
      <div>
        <div class="section-label">关于烟火厨房</div>
        <h2 class="section-title">一间有温度的厨房</h2>
        <p class="section-desc">烟火厨房成立于 2006 年，我们相信食物是连接人与人之间最朴素也最温暖的方式。从选料到出品，每一个环节都秉持"地道本味"的理念——不取巧、不浮华，只做好菜。</p>
        <div class="about-stats">
          <div class="stat" v-for="s in stats" :key="s.label">
            <div class="stat-num">{{ s.num }}</div>
            <div class="stat-label">{{ s.label }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const stats = [
  { num: '8+', label: '年匠心沉淀' },
  { num: '50+', label: '道精致菜品' },
  { num: '4.9', label: '大众点评评分' }
]
</script>
