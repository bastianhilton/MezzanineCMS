<template>
  <v-app>
    <section class="menu cid-tN2lVFAcUB" once="menu" id="menu01-0">



      <nav class="navbar navbar-dropdown navbar-expand-lg">
        <div class="container">
          <div class="navbar-brand">
            <span class="navbar-logo">
              <a href="/">
                <span class="p-2 mbr-iconfont mobi-mbri-success mobi-mbri"></span>
              </a>
            </span>
            <span class="navbar-caption-wrap"><a class="navbar-caption text-secondary mbr-bold display-5"
                href="/">MezzanineCMS</a></span>
          </div>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
            aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
            <div class="hamburger">
              <span></span>
              <span></span>
              <span></span>
              <span></span>
            </div>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav nav-dropdown" data-app-modern-menu="true">
              <li class="nav-item"><a class="nav-link link text-secondary firstlink text-primary display-7"
                  href="https://mezzanine.readthedocs.io/en/latest/overview.html#third-party-plug-ins"
                  aria-expanded="false" target="_blank">Modules</a></li>

              <li class="nav-item">
                <a class="nav-link link text-primary display-7" href="/features" aria-expanded="false">Features</a>
              </li>
              <li class="nav-item"><a class="nav-link link text-primary display-7"
                  href="https://mezzanine.readthedocs.io/en/latest/overview.html#sites-using-mezzanine"
                  aria-expanded="false" target="_blank">Showcase</a></li>
              <li class="nav-item"><a class="nav-link link text-primary display-7"
                  href="https://mezzanine.readthedocs.io/en/latest/" aria-expanded="false"
                  target="_blank">Documentation</a></li>
            </ul>
            <div class="navbar-buttons mbr-section-btn"><a class="btn btn-sm btn-primary-outline mbr-semibold display-7"
                href="https://mezzanine.readthedocs.io/en/latest/overview.html#installation" target="_blank">
                Download
              </a></div>

          </div>
        </div>
      </nav>
    </section>

    <v-main>
      <v-card>
        <v-layout>
          <v-main id="sidebarNav"></v-main>
          <main id="mainSection">
            <slot />
          </main>
        </v-layout>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
  import search from '../components/Search/search.vue'

  export default {
    components: {
      search
    },
    data() {
      return {
        drawer: null,
        location: 'bottom',
        rail: true,
        loaded: false,
        loading: false,
      }
    },

    methods: {
      onClick() {
        this.loading = true

        setTimeout(() => {
          this.loading = false
          this.loaded = true
        }, 2000)
      },
    },
  }
</script>

<script setup>
  import {
    ref
  } from 'vue'

  const theme = ref('light')

  function onClick() {
    theme.value = theme.value === 'light' ? 'dark' : 'light'
  };
</script>