<template>
<div>
  <Banner />
  <Search class="search" @getItems="getSearchItems" />
  <CardList :items="items" v-if="items.length > 0" />
</div>
</template>

<script>
import Banner from '@/components/Banner';
import Search from '@/components/Search';
import CardList from '@/components/CardList';

export default {
  components: {
    Banner,
    Search,
    CardList,
  },
  data () {
    return {
      items: [],
    }
  },
  methods: {
    getSearchItems: function(items) {
      this.items = items
    }
  }
};
</script>

<style scoped>
.search {
  margin-top: 300px;
}
</style>
