<template>
  <div class="form-container">
  <div :style="{ backgroundColor: myColor }"
   <form @submit.prevent="sendRequest()" @keydown.prevent.enter>
    <b-field label="Name">
      <b-input v-model="contact.name"></b-input>
    </b-field>
    <b-field label="Surname">
      <b-input v-model="contact.surname"></b-input>
    </b-field>
    <b-field label="Email">
      <b-input type="email" v-model="contact.email" maxlength="30"></b-input>
    </b-field>
    <b-field label="Message">
        <b-input maxlength="200" v-model="contact.message" type="textarea"></b-input>
    </b-field>
    <label>Showit </label>
    <input type="checkbox" v-model="contact.active"></input><br>
    <label>Male </label>
    <input type="radio" value="male" v-model="contact.gender"></input><br>
    <label>Female </label>
    <input type="radio" value="female" v-model="contact.gender"></input><br>
    <ul>
    <li v-for="name in contact.myArray">{{ name }}</li>
    </ul>
    <select v-model="contact.selection">
    <option>male</option>
    <option>female</option>
    <option>none</option>
    </select><br>
    <input v-show="vshow" type="submit" value="Send request" class="is-primary">
   </form>
   <div class="result" v-if="submit">
     <div class="columsns">
       <div v-for="(item, index) in submitions" :key="index" class="column is-4">
          <h3 class="submition-id">Submition number {{ index }}</h3>
          <strong>Name:</strong> {{item.name}}<br/>
          <strong>Surname:</strong> {{item.surname}}<br/>
          <strong>Email:</strong> {{item.email}}<br/>
          <strong>Message:</strong> {{item.message}}<br/>
       </div>
     </div>
   </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'ContactForm',
  data:() => ({
    vshow: true,
    contact: {
      name: '',
      surname: '',
      email: '',
      message: '',
      active: true,
      gender: 'male',
      myArray: ["Sara", "Tim", "Peter"],
      selection: '',
      myColor: "#22cc77",
    },
    hasError: true,
    submit: false,
    submitions: []
  }),
  methods: {
    sendRequest() {
      this.submit = true
      this.submitions.push(this.contact)
      console.log(this.contact)
    }
  }
}
</script>

<style lang="scss" scoped>
.is-primary {
    background-color: #7957d5;
    border-color: transparent;
    color: #fff;
    padding: 10px;
    cursor: pointer;
}

.is-primary:hover {
  background-color: #714dd2;
  border-color: strong;
  color: #fff;
}

.result {
    padding: 50px;
    margin-top: 50px;
}

.columns {
  flex-wrap: wrap;
}

.submition-id {
  font-size: 20px;
}
</style>
