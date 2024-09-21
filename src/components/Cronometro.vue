<template>
    <div>
      <h1>Cronômetro</h1>
      <div class="container">
        <div id="display">{{ formattedTime }}</div>
        <div class="buttons">
          <button @click="startStop">{{ isRunning ? 'Stop' : 'Start' }}</button>
          <button @click="reset">Reset</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'VueCronometro',
    data() {
      return {
        timer: null,
        isRunning: false,
        hours: 0,
        minutes: 0,
        seconds: 0
      };
    },
    computed: {
      formattedTime() {
        return `${String(this.hours).padStart(2, '0')}:${String(this.minutes).padStart(2, '0')}:${String(this.seconds).padStart(2, '0')}`;
      }
    },
    methods: {
      startStop() {
        if (!this.isRunning) {
          this.startTimer();
        } else {
          this.stopTimer();
        }
        this.isRunning = !this.isRunning;
      },
      startTimer() {
        this.timer = setInterval(() => {
          this.seconds++;
          if (this.seconds === 60) {
            this.seconds = 0;
            this.minutes++;
            if (this.minutes === 60) {
              this.minutes = 0;
              this.hours++;
            }
          }
        }, 1000);
      },
      stopTimer() {
        clearInterval(this.timer);
      },
      reset() {
        this.hours = 0;
        this.minutes = 0;
        this.seconds = 0;
        if (this.isRunning) {
          this.stopTimer();
          this.isRunning = false;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  /* Estilos podem ser mantidos no style.css */
  </style>
  