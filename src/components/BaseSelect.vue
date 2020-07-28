<template>
    <div>
        <label v-if="label">{{ label }}</label>
        <select
                v-bind="$attrs"
                :id="label"
                :value="value"
                @input="updateValue">
            <option v-for="option in options"
                    :selected="option === value"
                    :value="option"
                    :key="option">
                {{ option }}
            </option>
        </select>

    </div>
</template>

<script>
  import { formFieldMixin } from '../mixins/formFieldMixin';

  export default {
    mixins: [ formFieldMixin ],
    props : {
      options: {
        type    : Array,
        required: true
      },
      value  : [ String, Number ],
    },
  };
</script>

<style scoped>

</style>