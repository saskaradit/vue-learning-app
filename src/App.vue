<template>
  <the-header title="Learning Resources"></the-header>
</template>

<script>
import TheHeader from './components/UI/TheHeader';

export default {
  components: {
    TheHeader
  },
  data() {
    return {
      storedResources: [
        {
          id: '124D',
          title: `Read The Fuckin' Manual`,
          description: 'The official Manual',
          link: 'https://youtube.com'
        },
        {
          id: '8121T',
          title: 'Read The Bread',
          description: 'The official Bread',
          link: 'https://google.com'
        }
      ]
    };
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
