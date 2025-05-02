<template>
  <div>
    <avc_select_options :options="list_options"/>
  </div>
</template>
<script>

import avc_select_options from './components/avc_select_options.vue'

export default {
  components: { avc_select_options },
  data() {
    return {
      list_options: [
        "Mac Computers",
        "Wearables and Accessories",
        "AirPods & Audio Products",
        "iCloud & iCloud+",
        "Apple Pay & Apple Card",
        "Apple Fitness+",
        "Magic Keyboard, Magic Mouse",
        "Apple TV HD (Discontinued)",

      ],
    }
  },
  methods: {

  }
}

</script>