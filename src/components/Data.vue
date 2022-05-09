<template>
    <div class="row">
        <h5>{{type}}</h5>
        <Item v-for="(item, index) in items" 
        v-bind:key="index" :passed-item="item" :type="type"></Item>
    </div>
</template>

<script>
import Item from './Item.vue'

export default {
    data() {
        return {
            type: this.$route.params.type,
            items: []
        }
    },
    watch: {
        '$route': 'fetchItems'
    },
    methods: {
        fetchItems() {
            this.items = []
            this.type = this.$route.params.type
            let initial_ids = [1, 5, 10, 15, 20, 25]

            for (let i in initial_ids) {
                let id = initial_ids[i]
                fetch(`https://swapi.dev/api/${this.type}/${id}`, {
        method: "GET"
      })
        .then(response => response.json())
        .then(json => (this.items.push(json)));
            }
        }
    },
    created() {
        this.fetchItems()
    },
    components: {
        Item
    }
}
</script>

