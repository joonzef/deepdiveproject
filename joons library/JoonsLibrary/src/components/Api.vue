<script>
export default {
  methods: {
    async fetchTwitch() {
      try {
        const response = await fetch(`https://id.twitch.tv/oauth2/token?client_id=3m8bnxaiypl0zoe0g1pazr8an1l0po&client_secret=n0rmv96v6ux6v1zlasqizl6nrv5g6r&grant_type=client_credentials`);

        if (!response.ok) {
          throw new Error(`HTTP error! status: ${response.status}`);
        }

        const data = await response.json();
        console.log(data);
      } catch (error) {
        console.error('An error occurred while fetching the Twitch token:', error);
      }
    }
  }
}
</script>