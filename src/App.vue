
<template>
 <div class="container p-4 box d-flex flex-column  align-items-center justify-content-center">

    <h1 class="text-center h-10 display-1 main-h1">Binary2Decimal</h1>
     <converter />
 </div>
</template>


<script>
import converter from './components/Converter.vue'

export default{
  name: 'App',
  components:{
    converter
  },
}
</script>
