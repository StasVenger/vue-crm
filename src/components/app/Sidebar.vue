<template>
  <ul class="sidenav app-sidenav" :class="{open: isOpen}">
    <router-link
        v-for="link in links"
        :key="link.url"
        custom
        v-slot="{href, route, navigate, isActive}"
        :to="link.url"
    >
      <li :class="[isActive && 'active']">
        <a :href="href" class="waves-effect waves-orange pointer" @click="navigate">{{ link.title }}</a>
      </li>
    </router-link>
  </ul>
</template>

<script>
export default {
  props: ['isOpen'],
  data: () => ({
    links: [
      {title: 'Счет', url: '/'},
      {title: 'История', url: '/history'},
      {title: 'Планирование', url: '/planning'},
      {title: 'Новая запись', url: '/record'},
      {title: 'Категории', url: '/categories'},
    ]
  })
}
</script>