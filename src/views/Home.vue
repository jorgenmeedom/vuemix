<template>
  <div class="home">
    <section class="hero">
      <div id="xxx">
        <!-- TODO Pga. cashing kan vi ikke bruge bongocat.png navnet -->
        <!-- <img :src="myPicture.src" width=200 v-bind:alt="myPicture.alt" v-bind:href="myPicture.href"> -->
        <img src="../bongocat.png" width=200 alt="bongocat" href="#">
      </div>
      <div class="hero-body">
        <div class="container">
          <h1 v-show="wantToShowTitle" class="title">{{ heading }} {{ input }}</h1>
          <div class="column is-8 is-paddingless">
            <h2 class="subtitle is-4">{{ subtitle }}</h2>
          </div>
          <a href="https://vuejs.org/" class="button is-large" id="learn">Min egen knap</a><br>

            <button class="btn btn-primary" v-on:click="SayHi">Klik her</button><br>
            <input type="checkbox" v-model="checkBoxActive"/><br>
            <b>{{ checkBoxActive }}</b><br>

            <input type="color" v-model="color"/><br>
            <b>{{ color }}</b><br>


            <input type="date"><br>
            <input type="datetime-local"><br>
            <input type="email"><br>
            <input type="file"><br>
            <input type="hidden"><br>
            <input type="image"><br>
            <input type="month"><br>
            <input type="number"><br>
            <input type="password"><br>

            <label>Male </label>
            <input type="radio" value="male" v-model="gender"/><br>
            <label>Female </label>
            <input type="radio" value="female" v-model="gender"/><br>
            <b>{{ gender }}</b><br>

            <input type="range"/><br>
            <input type="reset"/><br>
            <input type="search"/><br>

            <form action="/action_page.php" method="post">
              <label for="fname">First name:</label><br>
              <input type="text" id="fname" name="fname" value="John"><br>
              <label for="lname">Last name:</label><br>
              <input type="text" id="lname" name="lname" value="Doe"><br>
              <input type="submit" value="Submit"><br>
            </form>

            <input type="tel"><br>
            <input type="text"><br>

            <input type="time"><br>
            <input type="url"><br>
            <input type="week"><br>

            <ul>
            <li v-for="(value, index) in myArray" v-bind:key="index">{{ value }} ({{index}})</li>
            </ul>
            <select v-model="selection">
            <option>male</option>
            <option>female</option>
            <option>none</option>
            </select><br>
            <b> {{ selection }} </b><br>
            <input v-show="checkBoxActive" v-model="input" type="text" value="Skriv lige dit input"><br>
            <b> {{ input }} </b><br>

            <div>
              <div v-html="code"></div>
            </div>

            <div>
              <input v-model="input2" @keyup.13="output"/>
            </div>

          <button class="btn btn-primary" @click="a++">a++</button>
          <button class="btn btn-primary" @click="b++">b++</button>
          {{ compA }}
          {{ compB }}
          <!-- TODO kun den første klasse bidrager -->
          <div :class="{ myClass: active, myMy: active }"></div>

          <div id="xxx1">
            <div :style="{ backgroundColor: color, width: myValue, height: myValue }"></div>
          </div>

          <div id="xxx2">
            <h1 v-if="active">Hello</h1>
            <h1 v-else>Hi</h1>
          </div>

          <div id="xxx3">
            <h1 v-if="value == 1">1</h1>
            <h1 v-else-if="value == 2">2</h1>
            <h1 v-else-if="value == 3">3</h1>
            <h1 v-else>No viable value</h1>
          </div>

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
              <p>“Jeg øver mig på vue.js.”</p>
              <p>mvh</p>
              <p>Jørgen Meedom</p>
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
      myPicture: {src: "/img/bongocat.241eed31.png", alt: "bongocat", href: "#"},
      wantToShowTitle: true,
      heading: "Meedom: ",
      subtitle: "Her er undertitlen på mit projekt",
      color: "black",
      checkBoxActive: true,
      gender: 'male',
      selection: '',
      myValue: "200px",
      input: "Original",
      myArray: ["Sara", "Tim", "Peter"],
      code: "<b>Jørgen Meedom was here</b>",
      cards: 30,
      input2: "",
      a: 0,
      b: 0,
      active: true,
      value: 3,
    }
    },
    // Creating methods
    methods : {

        // Creating function
        SayHi: function(){
            alert("Welcome to this tutorial");
        },
        output: function(){
          alert(this.input2);
        },
      methA: function() {
        return this.a;
      },
      methB: function() {
        return this.b;
      }
    },
  // Creating computeds
  computed: {
    compA: function() {
      return this.a;
    },
    compB: function() {
      return this.b;
    }
  }
};

</script>

<style lang="scss" scoped>
.home {
  .hero {
    background: darkgray;
    h2.subtitle.is-4 {
      font-size: 18px;
      margin-bottom: 25px;
    }
  }

  .section {
    i.fa.fa-cog {
      font-size: 20px;
    }

    .columns.cards {
      font-size: 16px;
      margin-top: 3px;
    }
  }
}

.myClass{
  width: 100px;
  height: 100px;
  background-color: #22cc77;
}

.myMy{
  border: {
    border: 2px;
    solid: #000;
  }
}

</style>
