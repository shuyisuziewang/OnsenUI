<template>
  <ons-pull-hook>
    <slot></slot>
  </ons-pull-hook>
</template>

<script>
  export default {
    //--------------------------------
    // lifecycle hooks
    //--------------------------------

    // beforeCreate() {
    // },

    // created() {
    // },

    // beforeMount() {
    // },

    mounted() {
      this.$nextTick(function() {
        const el = this.$el;

        el.onAction = (done) => {
          this.$emit('action', done);
        };

        el.addEventListener('changestate', ({state}) => {
          this.$emit('changestate', {state});
        });
      })
    },

    // beforeUpdate() {
    // },

    // updated() {
    // },

    // activated() {
    // },

    // deactivated() {
    // },

    // beforeDestroy() {
    // },

    // destroyed() {
    // },
  };
</script>
