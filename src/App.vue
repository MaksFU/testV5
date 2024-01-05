<template>
  <div class="theme-switcher">
    <label for="theme-switch">Темная тема</label>
    <input type="checkbox" id="theme-switch" v-model="isDarkTheme" />

    <div :class="{ 'datetime-picker': true, 'dark-theme': isDarkTheme }">
      <label for="date">Выберите дату:</label>
      <input
          type="date"
          id="date"
          v-model="selectedDate"
          :class="{ 'date-input': true, 'dark-input': isDarkTheme }"
      />

      <label for="time">Выберите время:</label>
      <input
          type="time"
          id="time"
          v-model="selectedTime"
          :class="{ 'time-input': true, 'dark-input': isDarkTheme }"
      />

      <p>Выбранная дата: {{ selectedDate }}</p>
      <p>Выбранное время: {{ selectedTime }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedDate: '',
      selectedTime: '',
      isDarkTheme: false
    }
  }
}
</script>

<style>
:root {
  --bg-color: #ffffff;
  --text-color: #000000;
  --input-bg-color: #ffffff;
  --input-border-color: #d7d7d7;
}

.dark-theme {
  --bg-color: #1e1e1e;
  --text-color: #ffffff;
  --input-bg-color: #2d2d2d;
  --input-border-color: #373737;
}

.datetime-picker {
  font-family: 'Arial', sans-serif;
  border: 1px solid var(--input-border-color);
  padding: 10px;
  border-radius: 5px;
  background-color: var(--bg-color);
  color: var(--text-color);
}

.date-input,
.time-input {
  padding: 8px;
  margin: 5px 0;
  border: 1px solid var(--input-border-color);
  border-radius: 5px;
  background-color: var(--input-bg-color);
  color: var(--text-color);
}

.date-input:focus,
.time-input:focus {
  outline: none;
  border-color: #4e8cff;
}

.dark-input {
  background-color: var(--input-bg-color);
  color: var(--text-color);
}
</style>
