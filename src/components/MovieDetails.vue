<template>
  <main class="relative h-screen overflow-hidden">
    <div
      class="absolute inset-0 bg-gradient-to-r from-[rgba(10.5,31.5,73.5,1)] via-[rgba(10.5,31.5,73.5,0.9)] to-[rgba(10.5,31.5,73.5,0.8)]"
    ></div>

    <div class="relative z-10 mx-4 p-4 mt-8 max-w-6xl md:mx-auto md:p-8">
      <div
        class="flex flex-col items-center md:flex-row md:items-start md:space-x-8"
      >
        <img
          :src="movie.Poster"
          alt="Movie Poster"
          class="w-64 rounded-lg shadow-lg transform transition duration-300 hover:scale-105"
        />

        <div class="mt-6 text-center md:mt-0 md:text-left">
          <h1 class="text-4xl font-bold text-white">
            {{ movie.Title }}
            <span class="font-light text-gray-300">({{ movie.Year }})</span>
          </h1>
          <p class="mt-2 text-sm font-medium text-gray-400">
            {{ movie.Rated }} ․ {{ movie.Released }} ․ ({{ movie.Country }}) ․
            {{ movie.Genre }} ․ {{ movie.Runtime }}
          </p>
          <p class="mt-4 text-base text-gray-200 leading-relaxed">
            {{ movie.Plot }}
          </p>
          <p class="mt-2 text-sm font-medium text-gray-400">
            Director: {{ movie.Director }}
          </p>
          <p class="mt-2 text-sm font-medium text-gray-400">
            Writer: {{ movie.Writer }}
          </p>
          <p class="mt-2 text-sm font-medium text-gray-400">
            Actors: {{ movie.Actors }}
          </p>
          <p class="mt-2 text-sm font-medium text-gray-400">
            Language: {{ movie.Language }}
          </p>
          <p class="mt-2 text-sm font-medium text-gray-400">
            Awards: {{ movie.Awards }}
          </p>

          <div class="mt-4">
            <h2 class="text-lg font-semibold text-white">Ratings:</h2>
            <ul class="text-sm text-gray-400">
              <li v-for="rating in movie.Ratings" :key="rating.Source">
                {{ rating.Source }}: {{ rating.Value }}
              </li>
            </ul>
          </div>

          <div class="mt-6">
            <button
              @click="likeMovie"
              class="bg-red-600 text-white text-sm px-6 py-2 rounded-full shadow-md hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2"
            >
              ❤ Like
            </button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      movie: {},
    };
  },
  mounted() {
    this.fetchMovieData();
  },
  methods: {
    async fetchMovieData() {
      const response = await fetch(
        "http://www.omdbapi.com/?i=tt3896198&apikey=d2132124"
      );
      const data = await response.json();
      this.movie = data;
    },
    likeMovie() {
      alert("You liked this movie!");
    },
  },
};
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}

body {
  font-family: "Arial", sans-serif;
  margin: 0;
  padding: 0;
  background-color: #1a202c;
}
</style>
