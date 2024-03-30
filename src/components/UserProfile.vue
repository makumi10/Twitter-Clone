<template>
    <div class="user-profile">
      <div class="user-panel">
          <h1 class="user-name">@ {{  user.username }}</h1>

          <div class="admin-badge" v-if="user.isAdmin">
              Admin
          </div>
          <!-- <h1 class="full-name"> {{ fullName }}</h1> -->

          <div class="follow-count">
              <strong>Followers</strong> : {{ followers }}
          </div>

          <!-- <button @click="followUser">
              Follow
          </button> -->
      </div>

      <div class="user-tweets">
        <TweetItem v-for="tweet in user.tweets" :key="tweet.id" :username="user.username" :tweet="tweet"/>
      </div>
    </div>
</template>
  
<script> 

  import TweetItem from "./TweetItem";
  
  export default {
    name: 'App',
    components: { TweetItem },
    data(){
      return{
        followers: 0,
        user: {
          id: 1,
          username: "uixmakumi",
          firstName: "Brian",
          lastName: "Makumi",
          email: "bmakumi2000@gmail.com",
          isAdmin: true,
          tweets:[
            {id: 1, content: 'Hello World!'},
            {id: 2, content: 'Trying Twitter For the first time'}
          ]
        }
      }
    },
    watch: {
      followers(newFollowerCount, oldFollowerCount){
        if(oldFollowerCount < newFollowerCount){
          console.log(`${this.user.username} has gained a follower!`)
        }
      }
    },
    computed:{
      fullName() {
        return `${this.user.firstName} ${this.user.lastName}`;
      }
    },
    methods:{
      followUser(){
        this.followers++;
      }
    },
    mounted(){
      this.followUser();
    }
  }
</script>
  
  <style>

    .user-profile{
      display: grid;
      grid-template-columns:  1fr 3fr;
      max-width: 100%;
      padding: 50px 5%;
    }
    .user-panel{
      background-color: white;
      margin-right: 50px;
      border-radius: 10px;
      padding: 20px;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
    }
    .user-panel .user-name{
      font-weight: 500;
      font-size: 1rem;
    }
    .user-panel .admin-badge{
      background-color: red;
      color: white;
      border-radius: 5px;
      margin-right: auto;
      font-size: 10px;
      font-weight: 600;
      padding: 5px 2%;        
    }
  </style>
  