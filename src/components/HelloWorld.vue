<template>
  {{ data }}
</template>

<script>
import { useQuery } from 'villus'
export default {
  name: 'HelloWorld',
  async setup() {
    const { data } = await useQuery(`
      query AllPets ($category: PetCategory) {
        allPets (category: $category) {
          id
          name
          category
          photo {
            thumb
            full
          }
        }
      }
    `)
    return { data }
  }
}
</script>
