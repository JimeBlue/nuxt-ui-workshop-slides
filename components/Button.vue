<template>
  <button
    class="group relative flex items-center gap-2 rounded-lg bg-green-400 px-4 py-2 text-lg font-semibold text-white transition-all duration-300 ease-in-out hover:bg-green-600"
  >
    Hover me
    <span
      class="relative transition-transform duration-300 ease-in-out group-hover:translate-x-2"
    >
      👉
      <span
        class="absolute inset-0 -z-10 size-6 rounded-full bg-black opacity-10 blur-md"
      />
    </span>
  </button>
</template>
