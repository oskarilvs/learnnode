<script setup>
import { computed } from 'vue';
let props = defineProps({
    color: {
        type: String,
        required: false,
        validator(value, props) {
            return [
                'primary',
                'light',
                'dark',
            ].includes(value);
        }
    },
    primary: {
        type: Boolean,
        required: false,
    },
    light: {
        type: Boolean,
        required: false,
    },
    dark: {
        type: Boolean,
        required: false,
    },

});

let classNames = computed(() => {
    let names = [];
    if(props.primary){
        names.push('is-' + props.color);
    }
    if(props.light){
        names.push('is-light');
    }
    if(props.dark){
        names.push('is-dark');
    }
    console.log(props);
    return names.join(' ');
})
</script>

<template>
    <div class="notification is-light">
  <button class="delete"></button>
  Primar lorem ipsum dolor sit amet, consectetur adipiscing elit lorem ipsum
  dolor. <strong>Pellentesque risus mi</strong>, tempus quis placerat ut, porta
  nec nulla. Vestibulum rhoncus ac ex sit amet fringilla. Nullam gravida purus
  diam, et dictum <a>felis venenatis</a> efficitur.
</div>
</template>