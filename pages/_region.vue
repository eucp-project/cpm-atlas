<template>
<div>
    <h3>
        {{ region_key }}:{{ title }}
    </h3>
</div>

</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const region_key = params.region
    const index = await $content('index').fetch()
    const title = index.regions[region_key].name
    return {
      region_key,
      title
    }
  }
}
</script>
