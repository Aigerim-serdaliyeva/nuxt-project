<template>
  <div>
    <h2>Admin Page</h2>
  </div>
</template>


<script>
export default {
  layout: 'admin',
  middleware: ['admin-auth']
}
</script>
