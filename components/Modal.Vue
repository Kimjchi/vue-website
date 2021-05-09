<template>
  <v-container fluid v-bind:style="{ padding: '0px' }">
    <transition name="fade" appear>
      <div class="modal-overlay"
           @click="$emit('close')"></div>
    </transition>
    <transition name="pop" appear>
      <div class="modal"
           role="dialog"
      >
        <h1><slot name="modal-header"></slot></h1>
          <div class="modal-body">
            <slot name="modal-text"></slot>
          </div>
          <div class="modal-footer">
            <v-btn
              v-if="link"
              outlined
              style="margin: 6%"
              :href="link"
              target="_blank"
            >
              Link
            </v-btn>
          </div>
      </div>
    </transition>
  </v-container>
</template>

<script>
  export default {
    name: "ModalComponent",
    props: {
      link: String
    }
  }
</script>
