<template>
  <div
    class="
      flex
      justify-center
      items-center
      inset-x-0
      fixed
      bottom-16
      ml-4
      mr-4
      z-10
    "
  >
    <div class="bg-white shadow-lg rounded-lg lg:w-3/12 w-96">
      <div class="flex">
        <div>
          <img
            class="w-full rounded hidden md:block"
            src="/img/anri_timely_2.png"
            alt="Album Pic"
          />
        </div>
        <div class="w-full p-4">
          <div class="flex justify-between">
            <div>
              <h3 class="text-2xl text-grey-darkest font-medium">
                Windy Summer
              </h3>
              <p class="text-sm text-grey mt-1">Anri</p>
            </div>
            <div class="text-red-lighter">
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path
                  d="M10 3.22l-.61-.6a5.5 5.5 0 0 0-7.78 7.77L10 18.78l8.39-8.4a5.5 5.5 0 0 0-7.78-7.77l-.61.61z"
                />
              </svg>
            </div>
          </div>
          <div class="flex justify-between items-center mt-1">
            <div class="text-grey-darker m-3">
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path
                  d="M6.59 12.83L4.4 15c-.58.58-1.59 1-2.4 1H0v-2h2c.29 0 .8-.2 1-.41l2.17-2.18 1.42 1.42zM16 4V1l4 4-4 4V6h-2c-.29 0-.8.2-1 .41l-2.17 2.18L9.4 7.17 11.6 5c.58-.58 1.59-1 2.41-1h2zm0 10v-3l4 4-4 4v-3h-2c-.82 0-1.83-.42-2.41-1l-8.6-8.59C2.8 6.21 2.3 6 2 6H0V4h2c.82 0 1.83.42 2.41 1l8.6 8.59c.2.2.7.41.99.41h2z"
                />
              </svg>
            </div>
            <div class="text-grey-darker m-3">
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path d="M4 5h3v10H4V5zm12 0v10l-9-5 9-5z" />
              </svg>
            </div>

            <button
              @click.prevent="toggle"
              class="p-8 rounded-full bg-red-light shadow-lg"
            >
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path d="M5 4h3v12H5V4zm7 0h3v12h-3V4z" />
              </svg>
            </button>

            <div class="text-grey-darker m-3">
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path d="M13 5h3v10h-3V5zM4 5l9 5-9 5V5z" />
              </svg>
            </div>
            <div class="text-grey-darker m-3">
              <svg
                class="w-6 h-6 text-pink-600"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path
                  d="M5 4a2 2 0 0 0-2 2v6H0l4 4 4-4H5V6h7l2-2H5zm10 4h-3l4-4 4 4h-3v6a2 2 0 0 1-2 2H6l2-2h7V8z"
                />
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script >
export default {
  data() {
    return {
      audioLogItems: [],
      activeAudio: null,
      audios: [
        {
          id: "citypop",
          name: "WindySummer",
          file: new Audio("/audio/windysummer.mp3"),
          isPlaying: false,
        },
      ],
    };
  },

  methods: {
    play() {
      this.activeAudio.isPlaying = true;
      this.activeAudio.file.play();
      this.activeAudio.loop = true;
    },

    pause() {
      this.activeAudio.isPlaying = false;
      this.activeAudio.file.pause();
    },

    toggle() {
      //needs to be set to something, like first entry of array
      this.activeAudio = this.audios[0];
      this.activeAudio.isPlaying ? this.pause() : this.play();
    },
  },
};
</script>

<style>
</style>

