<template>
  <div class="container">
    <div>
      Work Here
      <ul>
        <li v-for="work in works" v-bind:key="work.title">
          {{ work.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  async asyncData ({ $content }: any) {
    const { works } = await $content('data/work').fetch()
    return {
      works
    }
  }
}
</script>
