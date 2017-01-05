<template>
  <div id="note-editor">

    <input type="text" :value="activeNoteTittle" @input="editTittle" @blur="clearTittle" class="form-control">
    <textarea
      :value="activeNoteText"
      @input="editNote"
      class="form-control">
    </textarea>
  </div>
</template>

<script>
import { editNote } from '../vuex/actions'
import { editTittle } from '../vuex/actions'

export default {

  vuex: {
    getters: {
      activeNoteText: state => state.activeNote.text,
      activeNoteTittle: state => state.activeNote.tittle
    },
    actions: {
      editNote,
        editTittle
    }
  }
}
</script>
