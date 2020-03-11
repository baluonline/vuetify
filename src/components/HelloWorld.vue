<template>
  <v-container>
    <v-sheet height="400">
      <v-calendar
        ref="calendar"
        :now="today"
        :value="today"
        :events="events"
        color="red"
        type="week"
        :event-margin-bottom="3"
        v-model="focus"
        :weekdays="weekdays"
      ></v-calendar>
    </v-sheet>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    today: new Date().toISOString().substr(0, 10),
    focus: "",
    weekdays: [0, 1, 2, 3, 4, 5, 6],
    events: [
      {
        name: "Weekly Meeting",
        start: "2020-03-10 00:00",
        end: "2020-03-10 24:00"
      }
    ]
  })
};
</script>

<style scoped>
.my-event {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  border-radius: 2px;
  background-color: #1867c0;
  color: #ffffff;
  border: 1px solid #1867c0;
  font-size: 12px;
  padding: 3px;
  cursor: pointer;
  margin-bottom: 1px;
  left: 4px;
  margin-right: 8px;
  position: relative;
}

.my-event.with-time {
  position: absolute;
  right: 4px;
  margin-right: 0px;
}
</style>