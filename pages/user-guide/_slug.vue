
<template>
  <article>
    <h1>{{ params.title }}</h1>
    <p>{{ params.content }}
      <br>
      <strong>Posted on <time :datetime="date">{{ params.date }}</time></strong>
    </p>
    <img :src="params.thumbnail">
  </article>
</template>

<script>
export default {
  async asyncData ({params}) {
    const fileContent = import(`~/content/user-guide/articles/${params.slug}.`)
    return {
      content: fileContent
    }
  }
}
</script>
