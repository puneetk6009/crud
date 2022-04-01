<template>
  <Crud />
</template>


<script>
import Crud from '@/components/Crud.vue'
export default {
  components: {
    Crud
  }
}
</script>



<style>
.crud_holder {
    display: flex;
}
.crud_holder > div {
    width: 50%;
}

</style>
