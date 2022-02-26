<script>
export default {
  data() {
    return {
      title: "Image Overlay",
      description:
        "Some quick example text to build on the card and make up the bulk of the card's content.",
      img_url: "https://picsum.photos/900/250/?image=3",
      cover: null,
    };
  },
  methods: {
    showModal() {
      this.$refs["text-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
    },
    onFileChange() {

    },
  },
};
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" /> -->

    <!-- <div class="wrapper">
      
    </div> -->
  </header>

  <main>
    <!-- <TheWelcome /> -->
    <!-- <HelloWorld /> -->
    <div>
      <b-card
        overlay
        :img-src="img_url"
        img-alt="Card Image"
        text-variant="white"
        :title="title"
      >
        <b-card-text>
          {{ description }}
        </b-card-text>
        <footer>
          <b-button variant="danger" v-b-modal.my-modal>Edit</b-button>
          
        </footer>
      </b-card>
      <b-modal id="my-modal"  title="Edit Content" size="xl">
        <title>Edit Content</title>
        <div>
          <b-form enctype="multipart/form-data">
            <b-container>
              <b-row>
                <b-col>
                  <b-form-group
                    id="frm-title"
                    label="Enter new title"
                    label-for="inp-title"
                  >
                    <b-form-input id="inp-title" v-model="title"></b-form-input>
                  </b-form-group>
                </b-col>
              </b-row>
              <b-row>
                <b-col>
                  <b-form-group
                    id="frm-description"
                    label="Enter new description"
                    label-for="inp-description"
                  >
                    <b-form-textarea
                      id="inp-description"
                      v-model="description"
                    ></b-form-textarea>
                  </b-form-group>
                </b-col>
              </b-row>
              <b-row>
                <b-col>
                  <b-form-group
                    id="frm-image"
                    label="Change image slide"
                    label-for="file"
                  >
                  <input ref="file" :change="onFileChange()"  type="file">
                  </b-form-group>
                </b-col>
              </b-row>
            </b-container>
          </b-form>
        </div>
      </b-modal>
    </div>
  </main>
</template>

<style>
/* @import './assets/base.css'; */

#app {
  /* max-width: 1280px; */
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  /* body {
    display: flex;
    place-items: center;
  } */

  #app {
    /* display: grid; */
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
