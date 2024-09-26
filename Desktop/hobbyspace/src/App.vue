<template>
  <div @dblclick="displayHobbyInfo(hobbies[0])" class="wrap">
    <div>
      <ul class="images">
        <li><img @click="displayHobbyInfo(hobbies[2])" src="./assets/01.png" alt="" /></li>
        <li><img src="./assets/02.png" alt="" /></li>
        <li><img src="./assets/03.png" alt="" /></li>
        <li><img src="./assets/04.png" alt="" /></li>
        <li><img src="./assets/05.png" alt="" /></li>
        <li><img src="./assets/06.png" alt="" /></li>
        <li><img @click="displayHobbyInfo(hobbies[1])" src="./assets/07.png" alt="" /></li>
      </ul>
    </div>
    
    <h2 class="no_screen">Okestro Hobbyspace</h2>
   
    <!-- <button @click="displayHobbyInfo(hobbies[0])">Go Main</button> -->
    <!-- <button @click="displayHobbyInfo(hobbies[1])">02</button>
    <button @click="displayHobbyInfo(hobbies[2])">03</button> -->
    <div v-if="displayedHobby" class="info">
      <img v-bind:src="displayedHobby.logo" />
      <div class="text">
      <h1>{{ displayedHobby.title }}</h1>
      <h2>{{ displayedHobby.date }}</h2>
      <h2>{{ displayedHobby.place }}</h2>
      <a v-bind:href="displayedHobby.link" target="_blank">More Info</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hobbies: [
        {
          logo: require("./assets/book_logo.png"),
          title: "Adult Book Club",
          date: "on Thursday PM 7:00",
          place: "in Karajan",
          link: "https://www.notion.so/f9b1d93b5a254cf0bacd43ba598ae9eb?v=33584a8e9e1d42d5952b8a61aec12dd4",
        },
        {
          logo: require("./assets/drink_logo.png"),
          title: "Drink Eat Fourm",
          date: "on Friday PM 7:00",
          place: "TBD",
          link: "https://oil-lift-05f.notion.site/b3cbb58b1a6844faab69cc5ff10f991c?v=e0f9c3531c6b463bab15e39df4664cfc",
        },
        {
          logo: require("./assets/game_logo.png"),
          title: "Gaming Human Inc",
          date: "on Saturday PM 7:00",
          place: "TBD",
          link: "https://oil-lift-05f.notion.site/5c87ad4af64a48138e514bb9ab137499?v=6d10e15b1fb849d18a4be87e5d82f42c",
        },
      ],
      displayedHobby: null,
    };
  },
  mounted() {
    this.displayedHobby = this.hobbies[0];
  },
  methods: {
    displayHobbyInfo(hobby) {
      this.displayedHobby = hobby;
    },
  },
};
</script>


<style>
h1 {
  font-size: 4rem;
}
h2,h3 {
  margin-top: 0;
}
.wrap {
  height: 100%;
}

.info a {
  font-size: 1.2rem;
  font-weight: 700;
   z-index: 99;
}

/* .info .text {
  z-index: 99;
} */
body {
  display: flex;
  flex-direction: column;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100vh;
}

.info {
  display: flex;
  justify-content: center;
  flex-direction: column;
 
}

.info > img {
  width: 120px;
  align-self: center;

}

.no_screen {
  display: none;
}

.images {
  display: flex;
  

}

.images li {
  list-style-type: none;
}

.images li img {
  position: absolute;
  
}

.images li:nth-child(1) img {
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
  cursor: pointer;
}

.images li:nth-child(2) img {
  top: 30%;
  left: 80%;
  transform: translate(-50%, -50%);
}

.images li:nth-child(3) img {
    top: 60%;
    left: 53%;
    transform: translate(-50%, -50%);
}

.images li:nth-child(4) img {
  top: 67%;
  left: 10%;
  transform: translate(-50%, -50%);
}

.images li:nth-child(5) img {
  top: 47%;
  left: 30%;
  transform: translate(-50%, -50%);
}

.images li:nth-child(6) img {
    width: 220px;
    top: 55%;
    left: 83%;
    transform: translate(-50%, -50%);
}

.images li:nth-child(7) img {
    top: 24%;
    left: 21%;
    transform: translate(-50%, -50%);
    cursor: pointer;
}
</style>

