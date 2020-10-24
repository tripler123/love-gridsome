<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />

    <h1>Hello, world!</h1>
  <ul>
    <li v-for="post in $page.allBlogPost.edges" :key="post.nodeid">
      <a :href="post.node.path"
      >{{ post.node.title }} (posted on {{ post.node.date }})
      </a>
    </li>
  </ul>
  </Layout>
</template>

<page-query>
  query{
    allBlogPost {
      edges {
        node {
          title 
          date(format: "MMM DD")
          path
        }
      }
    }
  }
</page-query>


<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
