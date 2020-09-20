/* eslint-disable vue/require-v-for-key */
<template>
  <div class="container">
    <br />
    <br />
    <br />
    <b-row>
      <b-col cols="4">
        <b-img
          v-bind="mainProps"
          rounded
          src="https://scontent.fbkk12-3.fna.fbcdn.net/v/t1.0-9/118920358_2823651957918852_4591020093238173501_n.jpg?_nc_cat=102&_nc_sid=730e14&_nc_ohc=5dRm6iX_zwoAX-UUVcf&_nc_ht=scontent.fbkk12-3.fna&oh=06968e7d7b0b29d35cc736e4b602562c&oe=5F8C9A14"
          style="width: 30%;"
        ></b-img>
        <h1 id="text">Nonog_music</h1>
        <input type="text" v-model="textSearch " placeholder="Search" />
        <button @click="searchData()">Search</button>
      </b-col>
      <b-col cols="8">
        <div class="mt-4" v-for="list in playList" :key="list.trackId">
          <b-card no-body class="overflow-hidden" style="width: 100%;" border-variant="info">
            <b-row no-gutters>
              <b-col md="2">
                <b-card-img :src="list.artworkUrl60" :alt="list.artistName" class="rounded-0"></b-card-img>
              </b-col>
              <b-col md="10">
                <b-card-body :title="list.trackName">
                  {{ list.trackId }}
                  <b-card-text>
                    <audio controls>
                      <source :src="list.previewUrl" type="audio/mpeg" />
                    </audio>
                  </b-card-text>
                </b-card-body>
              </b-col>
            </b-row>
          </b-card>
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      playList: null,
      textSearch: "",
    };
  },

  methods: {
    searchData() {
      axios
        .get(
          "https://itunes.apple.com/search?term=+" +
            this.textSearch +
            "&limit=100"
        )
        .then((response) => {
          this.playList = response.data.results.slice(1, 15);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
#text {
  color: rgb(0, 0, 0);
}
</style>