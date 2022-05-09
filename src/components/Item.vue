<template>
  <div class="col-md-4">
    <div class="item-card card mb-3">
      <div class="card-body">
        <h4 class="card-title">{{item.name}}</h4>
        <hr>
        <div v-for="(value, key, index) in item">
            <div  class="card-text" v-if="index < 6">
                <strong>{{key}}</strong> : {{value}}
            </div>
        </div>
        <button class="btn" @click="switchItem">switch item</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["passedItem", "type"],
  data() {
      return {
          item: {

          }
      }
  },
  methods: {
    switchItem() {
        let random_id = Math.floor(Math.random() * 60) + 1;
        fetch(`https://swapi.dev/api/${this.type}/${random_id}`, {
        method: "GET"
      })
        .then(response => response.json())
        .then(json => this.item = json);
    }
  },
  created() {
      this.item = this.passedItem
  }
};
</script>
