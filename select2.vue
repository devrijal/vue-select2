<template>
  <select>
    <slot></slot>
  </select>
</template>

<script>
module.exports = {
  name: "select2",
  props: ["options", "value", 'modalId'],
  mounted: function() {
    let vm = this;
    if (this.modalId) {
      $(`#${this.modalId}___BV_modal_content_`).removeAttr('tabindex');
    }
    $(this.$el)
        // init select2
        .select2({ data: this.options })
        .val(this.value)
        .trigger("change")
        // emit event on change.
        .on("change", function() {
          vm.$emit("input", this.value);
        });
  },
  watch: {
    value: function(value) {
      // update value
      $(this.$el)
          .val(value)
          .trigger("change");
    },
    options: function(options) {
      // update options
      $(this.$el)
          .empty()
          .select2({ data: options });
    }
  },
  destroyed: function() {
    $(this.$el)
        .off()
        .select2("destroy");
  }
}
</script>

<style scoped>

</style>