<template>
  <form @submit.prevent="submitForm">
    <div class="form-container">
      <div class="form-control">
        <label for="user-name">Your Name:</label>
        <input id="user-name" name="user-name" type="text" v-model.trim="userName"/>
      </div>
      <div class="form-control">
        <label for="referrer">What do you use for your social links?</label>
        <select id="referrer" name="referrer" v-model="referrer">
          <option value="google">Google</option>
          <option value="Linkedin">Linkedin</option>
          <option value="Discord">Discord</option>
        </select>
      </div>
      <div class="form-control">
        <div>
          <input id="interest-news" name="interest" type="checkbox" value="communication" v-model="interest"/>
          <label for="interest-news">Communication</label>
        </div>
        <div>
          <input
              id="interest-tutorials"
              name="interest"
              type="checkbox"
              value="tutorials"
              v-model="interest"
          />
          <label for="interest-tutorials">Tutorials</label>
        </div>
        <div>
          <input
              id="interest-nothing"
              name="interest"
              type="checkbox"
              value="nothing"
              v-model="interest"
          />
          <label for="interest-nothing">Nothing</label>
        </div>
      </div>
      <button>
        Submit
      </button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ['set-data'],
  data() {
    return {
      userName: '',
      referrer: '',
      interest: []
    }
  },
  methods: {
    submitForm() {

      this.$emit('set-data', this.userName, this.referrer, this.interest);
      // if (this.userName === "") {
      //   console
      // }
      console.log('========UserName========');
      console.log('UserName:', this.userName);
      console.log('========Referrer========');
      console.log('Referrer: ' + this.referrer);
      console.log('========Checkboxes========');
      console.log('Checkbox:', this.interest);
    }
  }
}
</script>

<style scoped>

form {
  margin: 2rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 2rem;
  background-color: #ffffff;
  text-align: left;
}

.form-control {
  margin: 0.5rem 0;
}

.form-control.invalid input {
  border-color: red;
}

.form-control.invalid label {
  color: red;
}

label {
  font-weight: bold;
}

h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}

select {
  width: auto;
}

input[type='checkbox'],
input[type='radio'] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}

button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  cursor: pointer;
  padding: 0.75rem 3rem;
  border-radius: 30px;
  margin-top: 1.5rem;
}

button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}

</style>
