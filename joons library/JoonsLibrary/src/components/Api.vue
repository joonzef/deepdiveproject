<template>
  <div>
  </div>
</template>

<script>
export default {
  name: 'twitchApi',
  data: function () {
    return {
      gamesList: []
    }
  },
  methods: {
    fetchGames: function () {
      let fetchLink = 'https://api.twitch.tv/helix/games/top?first=10'

      fetch(fetchUrl, {
        method: `get`,
        headers: new Headers({
          'authorization': 'bearer' + import.meta.env.VITE_TWITCH_OAUTH,
          'Client-Id': import.meta.env.VITE_TWITCH_CLIENT_ID
        })
      })
      .then(
        function (response) {
          return response.json();
        }
      )
      .then(
        data => {
          console.log(data)
        }
      );
      },
      mounted () {
        console.log('Component mounted.');
        this.fetchGames();
      }
  }
}
</script>