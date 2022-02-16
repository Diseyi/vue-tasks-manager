<template>
  <div class="text-center border p-4 w-2/3 m-auto mt-20 lg:w-2/5">
    <img
      :src="picture"
      :alt="`${{ firstname }} ${{ lastname }} `"
      class="block m-auto rounded-full"
      :class="gender"
    />
    <h1 class="text-2xl">{{ firstName }} {{ lastName }}</h1>
    <h3 class="text-2xl">Email: {{ email }}</h3>
    <button
      v-on:click="getUser()"
      class="mt-10 border px-6 py-2 text-white font-semibold rounded"
      :class="gender"
    >
      Get Random User
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: "John",
      lastName: "Doe",
      email: "doe@gmail.com",
      gender: "male",
      picture: "https://randomuser.me/api/portraits/men/75.jpg",
    };
  },
  methods: {
   async getUser () {
     const res = await fetch('https://randomuser.me/api/')
     const {results} = await res.json()
     console.log(results)


      this.firstName = results[0].name.first
      this.lastName = results[0].name.last
      this.email = results[0].email
      this.gender = results[0].gender
      this.picture = results[0].picture.large
    },
  },
};
</script>

<style>
.male {
  border: 4px solid skyblue;
  background: skyblue;
}

.female {
  border: 4px solid pink;
  background: pink;
}
</style>