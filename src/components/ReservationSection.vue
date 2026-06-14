<template>
  <section class="reservation" id="reserve">
    <div class="section-label">预订</div>
    <h2 class="section-title">预留您的位置</h2>
    <p class="section-desc">留下您的信息，我们会尽快确认预订。</p>
    <form class="reservation-form" @submit.prevent="handleReserve">
      <input type="text" placeholder="您的姓名" v-model="form.name" required>
      <input type="tel" placeholder="手机号码" v-model="form.phone" required>
      <input type="date" v-model="form.date" required>
      <select v-model="form.guests" required>
        <option value="" disabled selected>用餐人数</option>
        <option>2 人</option>
        <option>3-4 人</option>
        <option>5-6 人</option>
        <option>7-10 人</option>
        <option>10 人以上</option>
      </select>
      <button type="submit" class="btn btn-primary">提交预订</button>
    </form>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  name: '',
  phone: '',
  date: '',
  guests: ''
})

function handleReserve() {
  alert('感谢 ' + form.name + ' 的预订！我们会尽快与您确认。')
  form.name = ''
  form.phone = ''
  form.date = ''
  form.guests = ''
}
</script>
