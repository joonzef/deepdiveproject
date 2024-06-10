<template>
  <div>
  </div>
</template>

<script>
export default {
  methods: {
    async fetchTwitch() {
      try {
        console.log(import.meta.env.VITE_FORTNITE);
        const response = await fetch(import.meta.env.VITE_TWITCH_LINK, {
          method: 'POST'
        });

        if (!response.ok) {
          throw new Error(`HTTP error! status: ${response.status}`);
        }

        const data = await response.json();
        console.log(data);
      } catch (error) {
        console.error('An error occurred while fetching the Twitch token:', error);
      }
    }
  },
  created() {
    this.fetchTwitch();
  }
}
</script>