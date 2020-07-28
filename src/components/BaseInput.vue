<template>
    <div class="field">
        <!-- this is where attributes will be inherited  if
     I not use the inheritAttrs: false
     regarder dans le input : v-bind
     -->
        <label v-if="label">{{ label }}</label>
        <input
                v-bind="$attrs"
                :id="label"
                :value="value"
                @input="updateValue"
        />
    </div>
</template>

<script>
  import { formFieldMixin } from '../mixins/formFieldMixin';

  export default {
    mixins: [ formFieldMixin ],
    props : {
      label: String
    },
  };
</script>
