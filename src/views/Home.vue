<template>
  <div class="home">
    <section class="hero">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">{{ heading }} {{ input }}</h1>
          <div class="column is-8 is-paddingless">
            <h2 class="subtitle is-4">{{ subtitle }}</h2>
          </div>
          <a href="https://vuejs.org/" class="button is-large" id="learn">Learn more</a><br>

            <button class="btn btn-primary" v-on:click="SayHi">Click</button><br>
            <input type="checkbox" v-model="active"></input><br>
            <p>{{ active }}</p>
            <label>Male </label>
            <input type="radio" value="male" v-model="gender"></input><br>
            <label>Female </label>
            <input type="radio" value="female" v-model="gender"></input><br>
            <ul>
            <li v-for="name in myArray">{{ name }}</li>
            </ul>
            <select v-model="selection">
            <option>male</option>
            <option>female</option>
            <option>none</option>
            </select><br>
            <input v-show="active" v-model="input" type="text" value="Skriv lige dit input"><br>

            <b> {{ input }} </b><br>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column is-1 has-text-centered">
            <i class="fa fa-cog"></i>
          </div>
          <div class="column is-4 has-text-centered">
            <h1 class="title">Lorem ipsum</h1>
          </div>
          <div class="column is-7 has-text-left" >
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam voluptatibus, quaerat ut culpa quidem illo ab eaque praesentium, placeat perferendis ea aliquid explicabo nemo, aspernatur sit laborum hic nesciunt laudantium.
          </div>
        </div>
      </div>

      <div class="columns cards">
        <div class="column" v-for="(index) in cards" :key="index">
          <div class="card">
            <div class="card-content">
              <p>“There are two hard things in computer science: cache invalidation, naming things, and off-by-one errors.”</p>
              <p>Jeff Atwood</p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      heading: "Meedom: ",
      subtitle:
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla eaque itaque magnam quaerat vero tenetur quidem ipsum suscipit a. Similique explicabo architecto ipsum quod laudantium ratione consequatur distinctio officia impedit?",
      cards: 30,
      active: true,
      gender: 'male',
      myArray: ["Sara", "Tim", "Peter"],
      selection: '',
      myColor: "#22cc77",
      input: "Original",
    }
    },
    // Creating methods
            methods : {

                // Creating function
                SayHi: function(){
                    alert("Welcome to this tutorial");
                }
            }
};
</script>

<style lang="scss" scoped>
.home {
  .hero {
    background: #28e8e8;
    h2.subtitle.is-4 {
      font-size: 8px;
      margin-bottom: 25px;
    }
  }

  .section {
    i.fa.fa-cog {
      font-size: 4px;
    }

    .columns.cards {
      font-size: 6px;
      margin-top: 3px;
    }
  }
}
</style>
