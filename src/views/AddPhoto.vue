<template>
  <input type="file" @change="onFileChange" />
</template>

<script>
  import axios from "axios";
  export default {
  methods: {
    onFileChange(e) {
      const formData = new FormData();
      formData.append("image", e.target.files[0]);
      console.log(formData)
      axios
        .post("/api/v1/add-image/", formData)
        .then(() => {
          console.log("SUCCESS");
        })
        .catch(() => {
          console.log("FAILED");
        });
    },
  },
}
</script>
