 
<template>
  <div class="tw-relative tw-inline-block tw-w-64">
  <button 
    @click="open = !open"
    class="tw-w-full tw-p-2 tw-bg-white tw-rounded-md tw-border tw-border-gray-300 tw-shadow-md focus:tw-outline-none focus:tw-ring-2 focus:tw-ring-blue-500"
  >
    Select Behavior
  </button>

  <ul
    v-if="open"
    class="tw-absolute tw-z-10 tw-mt-2 tw-w-full tw-bg-white tw-rounded-md tw-shadow-lg tw-border tw-border-gray-200 tw-transition-all tw-duration-300 tw-ease-in-out tw-transform tw-origin-top"
    :class="open ? 'tw-scale-y-100' : 'tw-scale-y-0'"
    style="transform-origin: top;"
  >
    <li
      v-for="(behaviour, index) in attReport"
      :key="index"
      @click="selectBehaviour(behaviour)"
      :class="['tw-px-4 tw-py-2  tw-cursor-pointer', behaviour.bgColor]"
    >
      {{ behaviour.name }}
    </li>
  </ul>
</div>

</template>

<script>
export default {
  data() {
    return {
      open: false, // Controls dropdown visibility
      attReport: [
        { name: "Excellent", bgColor: "hover:tw-bg-green-200" },
        { name: "Good", bgColor: "hover:tw-bg-blue-200" },
        { name: "Average", bgColor: "hover:tw-bg-yellow-200" },
        { name: "Poor", bgColor: "hover:tw-bg-red-200" },
      ],
    };
  },
  methods: {
    selectBehaviour(behaviour) {
      console.log("Selected:", behaviour.name);
      this.open = false; // Close dropdown
    },
  },
};
</script>