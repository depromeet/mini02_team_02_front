<template>
<div>
  <Banner />
  <Search class="search" @getItems="getSearchItems" @pending="pendingData" />
  <CardList :items="items" v-if="items.length > 0 && !isPending" />
  <img class="loading" width=50 height=50 src="../assets/loading.gif" v-if="isPending" />
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
      isPending: false,
    }
  },
  methods: {
    getSearchItems: function(items) {
      this.items = items;
    },
    pendingData: function(status) {
      this.isPending = status;
    }
  }
};
</script>

<style scoped>
.search {
  margin-top: 300px;
}
.loading {
  margin-top: 100px;
}
</style>
