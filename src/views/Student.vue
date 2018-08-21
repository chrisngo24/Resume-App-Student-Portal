<template>
  <div class="home container">
    <h1>{{ message }}</h1>
    <div class="resume-body">
      <img class="photo" v-bind:src="photo" width="300" alt="Card image cap">
      <h3>Name: {{ first_name }} {{ last_name }}</h3>
      <h4>Email: {{ email }}</h4>
      <h5>Phone: {{ phone_number }}</h5>
      <h6>Bio: {{ bio }}</h6>
      <ul>
        <li>{{ linkedin }}</li>
        <li>{{ twitter }}</li>
        <li>{{ github }}</li>
        <li>{{ resume }}</li>
        <li>{{ linkedin }}</li>
      </ul>
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Your Resume",
      first_name: "Jenny",
      last_name: "Lopez", 
      email: "jenny@email.com", 
      phone_number: "(555) 867-5309", 
      bio: "My name is Jenny!, I'm from the block", 
      linkedin: "URL",
      twitter: "URL",
      website: "URL", 
      resume: "URL", 
      github: "URL",
      photo: "https://m.media-amazon.com/images/M/MV5BMTY0OTY3ODA3OV5BMl5BanBnXkFtZTcwMzMyMzQ1NQ@@._V1_UY317_CR32,0,214,317_AL_.jpg"
    };
  },
  created: function() {},
  methods: {},
  computed: {}
};
</script>