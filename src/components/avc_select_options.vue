<template>

  <div class="container">
    <div class="costumSelect">
      <div class="selectedLi" @click="toggleList">
        <div>{{ selectedItems[selectedItems.length - 1] || 'select an option' }}</div>
        <i :class="['fa', isOpen ? 'fa-angle-up' : 'fa-angle-down']" id="icon"></i>
      </div>

      <transition name="slide">
        <ul v-show="isOpen" class="list-container">
          <li v-for="(item, index) in list_options" @click="change_select(item)">{{ item }}</li>
        </ul>
      </transition>
    </div>
    <ul class="selected-list">
      <li v-for="(item, index) in selectedItems" @click="removeItems(index)">{{ item }} </li>
    </ul>

  </div>

</template>
<script>
export default {
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
      selectedItems: [],
      isOpen: false,

    }

  },
  methods: {
    toggleList() {
      this.isOpen = !this.isOpen
    },
    change_select(item) {
      if (!this.selectedItems.includes(item)) {
        this.selectedItems.push(item)
      }
      this.isOpen = false
      console.log(this.selectedItems);
    },
    removeItems(index) {
      this.selectedItems.splice(index, 1)
    }
  }
}
</script>