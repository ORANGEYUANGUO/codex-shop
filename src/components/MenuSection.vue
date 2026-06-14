<template>
  <section class="menu-section" id="menu">
    <div class="menu-header">
      <div class="section-label">招牌推荐</div>
      <h2 class="section-title">本季人气之选</h2>
      <p class="section-desc">由主厨亲自挑选，呈现当季最佳风味组合。</p>
    </div>
    <div class="menu-grid">
      <div class="menu-card" v-for="item in menuItems" :key="item.name">
        <div class="menu-card-img" :class="item.bgClass">{{ item.emoji }}</div>
        <div class="menu-card-body">
          <h3>{{ item.name }}</h3>
          <p>{{ item.desc }}</p>
          <div class="menu-card-footer">
            <span class="price">{{ item.price }}</span>
            <span class="tag">{{ item.tag }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const menuItems = [
  {
    name: '慢炖牛排骨',
    desc: '精选谷饲牛肋，低温慢炖 8 小时，配根茎泥与红酒汁。',
    price: '¥168',
    tag: '人气 #1',
    emoji: '🍅',
    bgClass: 's1'
  },
  {
    name: '时令沙拉 · 和牛塔塔',
    desc: '手工生菜、牛油果、溏心蛋与和牛塔塔，淋柚子醋汁。',
    price: '¥128',
    tag: '新正推荐',
    emoji: '🥜',
    bgClass: 's2'
  },
  {
    name: '炭烤青花鱼',
    desc: '滨离宫同款备长火，搭配味噌腌渍与紫苏叶，焦香四溢。',
    price: '¥98',
    tag: '主厨推荐',
    emoji: '🍳',
    bgClass: 's3'
  }
]
</script>
