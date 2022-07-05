<template>
  <nav class="main-header">
    <span>LOGO</span>
    <ul>
      <li v-for="item in menu">
      <router-link :to="item.path">
      {{ item.name }}
      </router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name: 'MainHeader',
    data() {
      return {
        menu: [
          {
            name: 'Home',
            path: '/'
          },
          {
            name: 'About',
            path: '/about'
          },
          {
            name: 'Contact',
            path: '/contact'
          }
        ]
      }
    }
  }
</script>

<style lang="scss">
.main-header {
 display: flex;
 justify-content: space-between;
 align-items: center;
 border-bottom: 1px solid lightgray;

  ul{
    display: flex;
    li {
      &:not(:last-child){
        font-weight: bold;
        margin-right: 16px;
        display: inline-block;
      }
    }
  }
}

</style>
