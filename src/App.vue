<template>
  <div id="wrapper">
    <nav class="navbar is-dark">
      <div class="navbar-category">
        <router-link to="/" class="navbar-item"><strong>Image gallery</strong></router-link>
        <a class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbar-menu">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div class="navbar-menu" id="navbar-menu">
        <div class="navbar-end">
          <router-link to="/witcher" class="navbar-item">Witcher</router-link>
          <router-link to="/cat" class="navbar-item">Cat</router-link>

          <div class="navbar-item">
            <div class="buttons">
              <router-link to="/add-photo" class="button is-success">Add</router-link>
              <router-link to="/log-in" class="button is-light">Log in</router-link>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <section class="section">
      <router-view/>
    </section>

    <footer class="footer">
      <p class="has-text-centered">Lukasz Mazurek 2023</p>
    </footer>
    <router-view/>
  </div>
</template>

<style lang="scss">
@import '../node_modules/bulma';
</style>
