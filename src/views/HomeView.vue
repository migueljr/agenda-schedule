<script setup>
  import VueCal from 'vue-cal'
  import 'vue-cal/dist/vuecal.css'

  const events = [
    {
      start: '2023-07-10 11:00',
      end: '2023-07-10 11:15',
      title: 'Miguel Santos',
      content: 'Evento Especial',
      class: 'leisure',
      split:1
    }
  ]
    
</script>

<style>
  .vuecal__event.leisure {background-color: rgba(253, 156, 66, 0.9);border: 1px solid rgb(233, 136, 46);color: #fff;}
  *{
    font-family: Arial;
  }
</style>

<template>
  <div>

    <vue-cal
      selected-date="2023-07-10"
      today-button
      :time-from="10 * 60"
      :time-to="17 * 60"
      :time-step="15"
      hide-weekends
      :snap-to-time="15"
      :disable-views="['years', 'year', 'month']"
      editable-events
      :activeView="'day'"
      :events="events"
      locale="pt-br"
      :split-days="[
        { label: 'A', color: 'blue', class: 'split1' },
        { label: 'B', color: 'green', class: 'split2' },
        { label: 'C', color: 'orange', class: 'split3' },
        { label: 'D', color: 'red', class: 'split4' }
      ]"
      sticky-split-labels
      class="vuecal--full-height-delete">
      <template #split-label="{ split, view }">
        <div style="display: flex; align-items: center;">
          <img src="https://cdn-icons-png.flaticon.com/512/86/86399.png" style="width: 20px;margin-right: 5px;" alt="">
          <strong>{{ split.label }}</strong>
        </div>
      </template>
    </vue-cal>
  </div>
</template>
