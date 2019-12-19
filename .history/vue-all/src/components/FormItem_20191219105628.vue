<template>
  <div>
    <label for>{{label}}</label>
    <div>
      <slot></slot>
      <p v-if="errorStatus">{{errorMessage}}</p>
    </div>
  </div>
</template>

<script>
import Schema from "async-validator";
export default {
  props: ["label", "prop"],
  inject: ["kForm"],
  data() {
    return {
      errorMessage: "",
      errorStatus: true
    };
  },
  mounted() {
    this.$on("validate", this.validator);
  },
  methods: {
    validator() {
      // console.log(this.label)
      const rules = this.kForm.rules[this.prop];
      let value = this.kForm.model[this.prop];
      const descriptor = { [this.prop]: rules };
      let schema = new Schema(descriptor);
      schema.validate({ [this.prop]: value }, errors => {
        if (errors) {
          this.errorMessage = error[0].message;
          this.errorStatus = true;
        } else {
          this.errorMessage = "";
          this.errorStatus = false;
        }
      });
    }
  }
};
</script>