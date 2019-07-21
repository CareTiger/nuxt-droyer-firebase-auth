<template>
  <section>

    <div>
      <div>
        <nuxt-link to="/protected">Protected</nuxt-link>
        <nuxt-link v-if="uid" to="/auth/signin">Logout</nuxt-link>
        <nuxt-link v-else to="/auth/signin">Sign In</nuxt-link>
      </div>
      <h2>Updated with Cookie check in nuxt server init</h2>
      <p>
        Unprotected page --- anyone can see this
      </p>
    </div>

      <div class="comments">
        <h2>comments</h2>
        <vue-disqus  shortname="sampyl" :identifier="page_id" ></vue-disqus>
      </div>

  </section>
</template>

<script>
  import { mapGetters } from 'vuex'

  export default {
    computed: {
      ...mapGetters('modules/user', [
        'uid'
      ])
    }
  }
</script>

<style>
  a {
    padding: 5px;
  }
  .comments {
    width: 50%;
    margin-left: 25%;
  }
</style>
