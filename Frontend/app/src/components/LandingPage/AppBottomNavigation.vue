<template>
  <div class="absolute bottom-1 w-screen">
    <div
      class="container mx-auto flex flex-row-reverse w-1/3 items-center justify-center gap-12"
      v-if="this.$route.name === 'about'"
    >
      <div class="previousPageItem btn btn-primary animate-wiggle">
        <button class="cursor-pointer capitalize">
          Continue
          <i class="fa fa-arrow-right"></i>
        </button>
      </div>
    </div>

    <div
      class="container mx-auto flex flex-row-reverse w-1/3 items-center justify-center gap-12"
      v-else
    >
      <div class="nextPageItem btn btn-primary animate-bounce">
        <button class="cursor-pointer">
          <i class="fa fa-arrow-alt-circle-right" />
        </button>
      </div>
      <div
        class="previousPageItem btn btn-primary animate-bounce transition delay-1000"
      >
        <button class="cursor-pointer">
          <i class="fa fa-arrow-alt-circle-left" />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>
