<template>
  <section
    class="container"
  >
    <b-row class="content-row">
      <b-col class="left-col" :class="leftStyle">
        <slot name="left-side" />
      </b-col>
      <b-col class="right-col" :class="rightStyle">
        <slot name="right-side" />
      </b-col>
    </b-row>
    <b-row 
      v-if="!noDivider"
      class="divider-row"
    >
      <b-col :class="dividerRight ? 'text-right' : 'text-left'">
        <b-img 
          v-if="dividerRight" 
          fluid 
          width="356" 
          height="30" 
          src="~/assets/images/divider-right.svg" 
          alt="Divider" 
        />
        <b-img 
          v-else 
          fluid 
          width="356" 
          height="30" 
          src="~/assets/images/divider-left.svg" 
          alt="Divider" 
        />
      </b-col>
    </b-row>
  </section>
</template>

<script>
export default {
  props: {
    dividerRight: {
      type: Boolean,
      default: false
    },
    leftStyle: {
      type: String,
      required: false
    },
    noDivider: {
      type: Boolean,
      default: false
    },
    rightStyle: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped>
.content-row {
  margin-bottom: 4.8rem;
}
</style>