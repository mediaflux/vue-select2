# Vue-Select2

Select2 component for Vue2

# Installation

```
yarn install --save v-select2
```

# Examples

```
<template>
  <form>
    <select2 :options="options"></select2>
  </form>
</template>
<script>
  import Select2 from 'vue-select2/src/Select2'

  export default {
  	data () {
  	  return {
  	  	options: [
  	  	  {
  	  	  	name: 'Name 1',
  	  	  	value: 'Value 1'
  	  	  }
  	  	]
  	  }
  	}
  	components: {
  	  'select2': Select2
  	}
  }
</script>  
```
