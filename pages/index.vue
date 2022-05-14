<template>
  <div>
    <v-row>
      <span class="text-h5 font-weight-bold">Recently Played</span>
      <v-spacer></v-spacer>
      <span class="caption grey--text mr-2">SEE ALL</span>
    </v-row>
    <v-row class="mt-5">
      <v-card rounded v-for="item in musicList()" :key="item.title" class="ma-2">
        <v-img :src="item.img" height="145" width="145" class="mx-4 mt-4"></v-img>
        <v-card-title>{{item.title}}</v-card-title>
        <v-card-subtitle class="mb-6">{{item.author}}</v-card-subtitle>
      </v-card>
    </v-row>
    <v-row class="mt-12">
      <v-col class="pa-0">
        <div class="text-h5 font-weight-bold mb-1">Pupular Albums</div>
        
      </v-col>
      <v-spacer></v-spacer>
      <span class="caption grey--text mr-2">SEE ALL</span>
    </v-row>
    <v-row class="mt-5">
      <v-card rounded v-for="item in musicList()" :key="item.title" class="ma-2">
        <v-img :src="item.img" height="145" width="145" class="mx-4 mt-4"></v-img>
        <v-card-title>{{item.title}}</v-card-title>
        <v-card-subtitle class="mb-6">{{item.author}}</v-card-subtitle>
      </v-card>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    music: [
      {
        title: "Manusia",
        author: "Tulus",
        img:
          "https://i.scdn.co/image/ab67616d0000b273b55d26c578e30129b0a7e86e"
      },
      {
        title: "Justice",
        author: "Justin Bieber",
        img: "https://i.scdn.co/image/ab67616d0000b273e6f407c7f3a0ec98845e4431"
      },
      {
        title: "Sisa Rasa",
        author: "Mahalini",
        img: "https://i.scdn.co/image/ab67616d0000b273cf312a99e7451a59ef915f83"
      },
      {
        title: "SOUR",
        author: "Olivia Rodrigo",
        img:
          "https://i.pinimg.com/236x/54/79/44/54794436b71840391593e0eedf63f782.jpg"
      },
      {
        title: "Terlanjur Mencinta",
        author: "Tiara Andini",
        img:
          "https://i.scdn.co/image/ab67616d00001e02937d621f0025409ee44285d1"
      }
    ]
  }),
  methods:{
    musicList(){
      const newArr = this.music.slice()
        for (let i = newArr.length - 1; i > 0; i--) {
            const rand = Math.floor(Math.random() * (i + 1));
            [newArr[i], newArr[rand]] = [newArr[rand], newArr[i]];
        }
        return newArr
    }
  }
};
</script>
