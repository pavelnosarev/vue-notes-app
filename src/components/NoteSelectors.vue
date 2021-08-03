<template>
  <div class="note-selectors">
    <NoteSelector
      v-for="note in notes"
      v-bind:note="note"
      v-bind:selectedNoteId="selectedNoteId"
      v-on:selectNote="selectNote"
      :key="note.id"
    />
  </div>
</template>

<script>
import NoteSelector from "./NoteSelector.vue";
export default {
  components: {
    NoteSelector,
  },
  data: function () {
    return {
      notes: [
        { id: 1, body: "this is my first note", timestamp: Date.now() },
        { id: 2, body: "this is my second note", timestamp: Date.now() },
        { id: 3, body: "this is my third note", timestamp: Date.now() },
        { id: 4, body: "this is my fourth note", timestamp: Date.now() },
      ],
      selectedNoteId: 1,
    };
  },
  methods: {
    selectNote: function (note) {
      this.selectedNoteId = note.id;
    },
  },
};