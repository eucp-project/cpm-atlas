<template>
<div>        
  <div v-for="(region,key) in regions" :key="key" class="flex flex-wrap">
    <div class="w-screen">
      <NuxtLink :to="key">
        <h3 class="text-2xl p-2 m-2">
          {{ region.name }}
        </h3>
      </NuxtLink>
    </div>
  </div>
</div>

</template>

<script>
export default {
  data () {
    return {
      regions: []
    }
  },
  async mounted () {
    const index = await this.$content('index').fetch()
    this.regions = index.regions
  }
}
</script>
