<template>
  <load-page-component />
  <main>
    <go-to-top-component />
    <header-component />
    <advantage-component />
    <features-component />
    <projects-component />
    <say-component />
    <posts-component />
    <footer-component />
  </main>
</template>

<script>
import LoadPageComponent from './components/LoadPageComponent.vue'
import GoToTopComponent from './components/GoToTopComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'
import AdvantageComponent from './components/AdvantageComponent.vue'
import FeaturesComponent from './components/FeaturesComponent.vue'
import ProjectsComponent from './components/ProjectsComponent.vue'
import SayComponent from './components/SayComponent.vue'
import PostsComponent from './components/PostsComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    LoadPageComponent,
    GoToTopComponent,
    HeaderComponent,
    AdvantageComponent,
    FeaturesComponent,
    ProjectsComponent,
    SayComponent,
    PostsComponent,
    FooterComponent,
  }
}
</script>

<style></style>
