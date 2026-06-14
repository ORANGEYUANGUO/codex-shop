<template>
  <section class="testimonials" id="reviews">
    <div class="section-label">食客心声</div>
    <h2 class="section-title">他们这样说</h2>
    <div class="testimonial-grid">
      <div class="testimonial-card" v-for="t in testimonials" :key="t.author">
        <div class="stars">{{ t.stars }}</div>
        <blockquote>"{{ t.quote }}"</blockquote>
        <div class="testimonial-author">— {{ t.author }}</div>
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    stars: '★★★★★',
    quote: '牛排骨入口即化，红酒汁配米饭根本停不下来。环境安静，服务周到，是家会反复来的店。',
    author: '林先生 · 常客'
  },
  {
    stars: '★★★★★',
    quote: '带爸妈来过两次，老人家夸菜做得用心。上菜速度刚好，不会催也不会等。',
    author: '王女士 · 家庭聚餐'
  },
  {
    stars: '★★★★★',
    quote: '商务宴请选了包间，菜品和服务都体面。侍酒师的搭配建议非常专业，客人很满意。',
    author: '张先生 · 商务宴请'
  }
]
</script>
