<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <Resume></Resume>
    </template>
    <template #movements>
      <Movements></Movements>
    </template>
  </Layout>

</template>

<script>

// Components Imports
import Layout from "@/components/Layout.vue";
import Header from "@/components/Header.vue";
import Resume from "@/components/Resume/index.vue";
import Movements from "@/components/Movements/index.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
  },
};

</script>
