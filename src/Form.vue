<template>
  <div>
    <pre>
      {{ JSON.stringify(formValue, null, 5) }}
    </pre>
  </div>
  <form @submit="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model="formValue.name" />
    </div>
    <div>
      <label for="profile">Summary</label>
      <input type="text" id="profile" v-model="formValue.profileSummary" />
    </div>
    <div>
      <label for="country">Country</label>
      <select name="" id="country" v-model="formValue.country">
        <option value="nepal">Nepal</option>
        <option value="usa">USA</option>
      </select>
    </div>

    <div>
      <label for="location">Location</label>
      <select name="" id="location" multiple v-model="formValue.location">
        <option value="">Select</option>
        <option value="nepal">Nepal</option>
        <option value="usa">USA</option>
      </select>
    </div>

    <div>
      <input
        type="checkbox"
        id="remote"
        v-model="formValue.remote"
        true-value="yes"
        false-value="no"
      />
      <label for="remote">Open to remote</label>
    </div>

    <div>
      <label>Skills</label>
      <input type="checkbox" id="html" value="html" v-model="formValue.skill" />
      <label for="html">HTML</label>
      <input type="checkbox" id="js" value="js" v-model="formValue.skill" />
      <label for="js">JS</label>
      <input type="checkbox" id="vue" value="vue" v-model="formValue.skill" />
      <label for="vue">Vue</label>
    </div>

    <div>
      <label>Exp</label>
      <input type="radio" id="0-2" value="0-2" v-model="formValue.experience" />
      <label for="0-2">0-2</label>

      <input type="radio" id="2-3" value="2-3" v-model="formValue.experience" />
      <label for="2-3">2-3</label>
    </div>

    <button>Submit</button>
  </form>
</template>

<script>
export default {
  name: "FormView",
  data() {
    return {
      formValue: {
        name: " ",
        profileSummary: " ",
        country: " ",
        location: [],
        remote: "no",
        skill: [],
        experience: "",
      },
    };
  },
  methods: {
    submitForm(event) {
      event.preventDefault();
      console.log("form values", this.formValue);
    },
  },
};
</script>

<style lang="scss" scoped></style>
