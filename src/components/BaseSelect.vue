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
  export default {
    inheritAttrs: false,
    props       : {
      options: {
        type    : Array,
        required: true
      },
      value  : [ String, Number ],
      label  : String
    },
    methods     : {
      updateValue( event ) {
        this.$emit( 'input', event.target.value );
      }
    }

  };
</script>

<style scoped>

</style>