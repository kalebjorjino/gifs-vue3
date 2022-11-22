<template>
  <div>
    <img  class="w-full h-60" :src="gif.images.original.url" :alt="gif.id" loading="lazy" />
    <div class="px-6 py-4">
        <div class="text-base font-medium text-gray-500 hover:text-gray-900">{{ gif.title }}</div>
    </div>
  </div> 
</template>

<script>
export default {
   props: ["gif"],
};
</script>

