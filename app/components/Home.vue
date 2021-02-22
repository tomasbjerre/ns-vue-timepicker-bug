<template>
  <Page>
    <StackLayout :key="hour + minute">
      <TimePicker @loaded="timePickerLoaded" @timeChange="onTimeChange" />
    </StackLayout>
  </Page>
</template>

<script>
export default {
  methods: {
    timePickerLoaded: function(args) {
      var timepicker = args.object;
      timepicker.ios.datePickerMode = 3;
    },
    onTimeChange: function(args) {
      const hour = args.object.hour;
      const minute = args.object.minute;
      alert("chang\nh:" + hour + " m:" + minute);
    }
  }
};
</script>

<style scoped lang="scss">
@import "~@nativescript/theme/scss/variables/blue";

// Custom styles
.fas {
  @include colorize($color: accent);
}

.info {
  font-size: 20;
  horizontal-align: center;
  vertical-align: center;
}
</style>
