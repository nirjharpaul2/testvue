<script>
import { ref } from "vue";

const functions = ref([
  { id: 0, name: "shirt" },
  { id: 1, name: "jacket" },
  { id: 2, name: "shoes" },
  { id: 3, name: "shoes" },
  { id: 4, name: "shoes" },
  { id: 5, name: "shoes" },
]);

const mytasks = ref([
  { id: 0, name: "shirt" },
  { id: 1, name: "jacket" },
  { id: 2, name: "shoes" },
]);

export default {
  name: "HomeView",
  data() {
    return {
      functions,
      mytasks,
    };
  },
};
</script>
<style scoped lang="scss">
.card-wrapper-div {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  padding: 5px 20px;
}
</style>

<template>
  <div class="home">
    <div>
      <div>
        <b-tabs content-class="mt-3" fill>
          <b-tab title="First" active>
            <div class="card-wrapper-div">
              <div
                v-for="(carddetails, index) in functions"
                :key="carddetails.id"
                ref="{{functions}}"
              >
                <div class="cardwrapper">
                  <b-card
                    title="Card Title"
                    img-src="https://picsum.photos/600/300/?image=25"
                    img-alt="Image"
                    img-top
                    tag="article"
                    style="max-width: 20rem"
                    class="mb-2"
                  >
                    <template #header>
                      <h4 class="mb-0">Hello World</h4>
                    </template>
                    <b-card-body>
                      <b-card-title>Card Title</b-card-title>
                      <b-card-sub-title class="mb-2"
                        >Card Sub Title</b-card-sub-title
                      >
                      <b-card-text>
                        {{ functions.name }} -- {{ index }}
                      </b-card-text>
                      <b-button href="#" variant="primary"
                        >Go somewhere</b-button
                      >
                    </b-card-body>
                    <b-card-footer>This is a footer</b-card-footer>
                  </b-card>
                </div>
              </div>
            </div>
          </b-tab>
          <b-tab title="Second">
            <div class="card-wrapper-div">
              <div
                v-for="(carddetails, index) in mytasks"
                :key="carddetails.id"
                ref="{{mytasks}}"
              >
                <div class="cardwrapper">
                  <b-card
                    title="Card Title"
                    img-src="https://picsum.photos/600/300/?image=25"
                    img-alt="Image"
                    img-top
                    tag="article"
                    style="max-width: 20rem"
                    class="mb-2"
                  >
                    <template #header>
                      <h4 class="mb-0">Hello World</h4>
                    </template>
                    <b-card-body>
                      <b-card-title>Card Title</b-card-title>
                      <b-card-sub-title class="mb-2"
                        >Card Sub Title</b-card-sub-title
                      >
                      <b-card-text>
                        {{ functions.name }} -- {{ index }}
                      </b-card-text>
                      <b-button href="#" variant="primary"
                        >Go somewhere</b-button
                      >
                    </b-card-body>
                    <b-card-footer>This is a footer</b-card-footer>
                  </b-card>
                </div>
              </div>
            </div>
          </b-tab>
        </b-tabs>
      </div>
    </div>
  </div>
</template>
