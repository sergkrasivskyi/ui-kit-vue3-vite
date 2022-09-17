<template>
  <div>
    <component :is="typeButton" :href="href" :class="['button', `button_${color}`]">
      <slot></slot>
    </component>


  </div>

</template>
<script setup>
// import { ref } from "vue"
// const typeComponent = ref('');
// setTypeComponent();
const props = defineProps({
  typeButton: {
    type: String,
    default: null
  },
  color: {
    type: String,
    default: "primary"
  },
  rounded: {
    type: Boolean,
    required: false
  },
  outlined: {
    type: Boolean,
    required: false
  },
  disabled: {
    type: Boolean,
    required: false
  },
  href: {
    type: String,
    default: null
  }
})
const typeButton = () => {
  href ? 'a' : 'button'
}
</script>
<style lang="scss" scoped>
.button {
  display: inline-block;
  margin: 0.5em 0;
  padding: 1em 2em;
  background: #fff;
  border: 2px solid tomato;
  border-radius: 3px;
  color: tomato;
  font-family: "Quicksand", sans-serif;
  font-size: 1em;
  font-weight: 700;
  letter-spacing: 0.02em;
  line-height: 1;
  text-decoration: none;
  text-transform: uppercase;
  cursor: pointer;
  transition: 0.3s;

  &_primary {
    background-color: var(--primary);
  }

  &_accent {
    background-color: var(--accent);
  }

  &_rounded {
    background-color: var(--accent);
    border-radius: 3rem;
  }

  &_outlined {
    background-color: transparent;
    outline-color: var(--accent);
    // border-radius: 3rem;
  }

}
</style>