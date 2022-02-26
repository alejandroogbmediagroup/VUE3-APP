<script>
export default {
  data() {
    return {
      title: "Image Overlay",
      description:
        "Some quick example text to build on the card and make up the bulk of the card's content.",
      img_url: "https://picsum.photos/900/250/?image=3",
    };
  },
  methods: {
    showModal() {
      this.$refs["text-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
    },
    changeContent() {
      // let formData = new FormData();
      // formData.append("cover", this.cover);
      // const config = {
      //   headers: {
      //     "content-type": "multipart/form-data",
      //   },
      // };
      // const url = "http://localhost/names";
      // axios
      //   .post(url, formData, config)
      //   .then((response) => {
      //     Toast.fire({
      //       icon: "success",
      //       title: response.data.msg,
      //     });
      //   })
      //   .catch((error) => {
      //     if (error.response) {
      //       console.log(error.response.data);
      //       console.log(error.response.status);
      //       console.log(error.response.headers);
      //       if (error.response.status === 422) {
      //         this.$refs.formData.setErrors(error.response.data.errors);
      //         Toast.fire({
      //           icon: "error",
      //           title: "Por favor, complete los campos requeridos",
      //         });
      //       }
      //     }
      //   });
    },
  },
};
</script>

<template>
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
    <b-modal id="my-modal">Hello From My Modal!</b-modal>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
