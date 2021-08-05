<template>
  <p id="wait">Click the box as fast as you can <br />when it pops up.</p>
</template>

<script>
import Block from "./Block";
export default {
  wait() {
    if (this.isPlaying) {
      this.wait = false;
    }
  },
};
</script>

<style>
#wait {
  color: purple;
}
</style>