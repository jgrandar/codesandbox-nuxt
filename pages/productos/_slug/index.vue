<template>
  <div>
    <h1>Producto {{ producto.nombre }}</h1>
    <p v-text="producto.desc"></p>
  </div>
</template>

<script>
export default {
  name: 'ProductoMostrar',
  async asyncData({ params, $axios }) {
    // const respuesta = await $axios.$get(`api/id/${params.id}.json`)
    // const respuesta = await $axios.$get(`api/slug/${params.slug}.json`)
    // const respuesta = await $axios.$get(`https://2h2md.sse.codesandbox.io/api/id/${params.id}.json`)
    const respuesta = await $axios.$get(`https://2h2md.sse.codesandbox.io/api/slug/${params.slug}.json`)

    return { producto: respuesta }
  },
  data() {
    return {
      producto: null,
    }
  },
}
</script>
