<template>
  <div class="flex items-center justify-center basis-1 gap-24s h-[100%]">
    <div class="relative left-40">
      <div
        class="flex flex-col justify-center items-start text-white pl-40s gap-3 border-0 py-10 bg-radial to-app-blue via-app-blue from-[#1B3549]"
      >
        <p class="font-bold text-lg uppercase font-app-default">
          <span class="text-[#E63F76]">Hello,</span>
          Im {{ user.name }}
        </p>
        <p class="font-bold text-7xl font-heading">
          {{ user.occupation }}
        </p>
        <p class="font-light text-gray-300 capitalize">
          {{ user.tagline }}
        </p>
        <div class="mt-3">
          <button class="btn btn-primary font-app-default uppercase rounded-[20px] px-4">
            Hire me
          </button>
        </div>
      </div>
    </div>

    <div class="flex items-center justify-end w-1/2">
      <div class="user-image w-1/2 h-1/2 relative right-20">
        <img :src="user.photo" alt="User" class="h-full" />
      </div>
    </div>
  </div>
  <div class="absolute right-0 bottom-10 border-no-right p-3">
    <div class="flex gap-5">
      <i class="fa-brands fa-discord text-[#49D6FB] text-2xl"></i>
      <i class="fa-brands fa-instagram text-[#49D6FB] text-2xl"></i>
      <i class="fa-brands fa-twitter text-[#49D6FB] text-2xl"></i>
      <i class="fa-brands fa-facebook text-[#49D6FB] text-2xl"></i>
      <i class="fa-brands fa-youtube text-[#49D6FB] text-2xl"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppAboutIntro",
  props: {
    user: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.bg-radial {
  background-image: radial-gradient(circle at center, var(--tw-gradient-stops));
}
</style>

<!--default: {-->
<!--name: "Philip Oluwatimileyin",-->
<!--occupation: "Graphics Designer",-->
<!--tagline: "I know that good design meant good business",-->
<!--},-->
