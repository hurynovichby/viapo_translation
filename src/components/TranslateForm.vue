<template>
  <div class="row" id="translateForm">
    <div class="col-md-8 mx-auto">
      <form v-on:submit="formSubmit">
        <div class="form-group">
          <textarea
            rows="6"
            class="ml-3 form-control"
            type="textarea"
            v-model="textToTranslate"
            placeholder="Введите текст"
          />
        </div>
        <div class="form-group">
          <select class="ml-3 form-control" v-model="language">
            <option value="ru">Русский</option>
            <option value="es">Испанский</option>
            <option value="fr">Французский</option>
          </select>
        </div>

        <input class="ml-3 btn btn-primary" type="submit" value="Перевести" />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "ru";
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
};
</script>

<style>
#transForm {
  border-radius: 10px;
  border: 1px #ccc solid;
}
</style>
