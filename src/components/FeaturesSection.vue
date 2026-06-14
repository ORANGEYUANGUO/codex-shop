<template>
  <section class="features" id="features">
    <div class="section-label">
      为什么选择我们 <span style="cursor:help;color:var(--gold)">?</span>
    </div>
    <h2 class="section-title">用心做好每一件事</h2>
    <div class="features-grid">
      <div class="feature-card" v-for="f in features" :key="f.title">
        <div class="feature-icon">{{ f.icon }}</div>
        <h3>{{ f.title }}</h3>
        <p>{{ f.desc }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
const features = [
  { icon: '🥬', title: '当日鲜采', desc: '每日清晨从本地农场直采，确保食材新鲜、当季、有来源。' },
  { icon: '👨‍🍳', title: '主厨匠心', desc: '20年经验的行政主厨，将传统技法与现代美学融汇于一盘。' },
  { icon: '🍞🧑', title: '雅致空间', desc: '暖木与石材打造的用餐环境，适合家庭聚餐、商务宴请或二人晚餐。' },
  { icon: '🍎', title: '精选酒单', desc: '涵盖国产精品与进口经典，侍酒师为您推荐与菜品最搭的那一瓶。' }
]
</script>
