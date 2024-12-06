<script>
export default {
  props: ["initialTask"],
  data() {
    return {
      task: this.initialTask || { name: "", description: "" },
    };
  },
  methods: {
    handleSubmit() {
      console.log(this.task);
      this.$emit("submit", this.task);
    },
  },
};
</script>

<template>
  <form
    @submit.prevent="handleSubmit"
    class="my-12 space-y-4 flex justify-between items-center flex-col"
  >
    <div>
      <label for="name" class="block text-sm/6 font-medium text-gray-900"
        >Name</label
      >
      <div class="mt-2">
        <input
          type="name"
          name="name"
          id="name"
          class="w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 disabled:cursor-not-allowed disabled:bg-gray-50 disabled:text-gray-500 disabled:outline-gray-200 sm:text-sm/6"
          placeholder="Enter name"
        />
      </div>
    </div>
    <div>
      <label for="email" class="block text-sm/6 font-medium text-gray-900"
        >Email</label
      >
      <div class="mt-2">
        <input
          type="email"
          name="email"
          id="email"
          class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 disabled:cursor-not-allowed disabled:bg-gray-50 disabled:text-gray-500 disabled:outline-gray-200 sm:text-sm/6"
          placeholder="Enter email address"
        />
      </div>
    </div>

    <button
      type="submit"
      class="rounded-md bg-indigo-500 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-400 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500"
    >
      Submit
    </button>
  </form>
</template>
