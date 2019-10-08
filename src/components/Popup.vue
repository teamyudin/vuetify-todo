<template>
    <v-dialog max-width="600px">
        <template v-slot:activator="{ on }">
        <v-btn class="success" small
        text
          v-on="on"
        >
          Add New Project
        </v-btn>
      </template>

    <v-card>
      <v-card-title>
        <h2>Add a New Project</h2>
      </v-card-title>

      <v-card-text>
        <v-form class="px-3">
          <v-text-field v-model="title" label="Title">
              <template slot="prepend">
                <v-icon>mdi-folder-outline</v-icon>
            </template>
          </v-text-field>
          <v-textarea v-model="content" label="Information" prepend-inner-icon="mdi-pencil-outline">
          </v-textarea>
          <v-spacer></v-spacer>

        <v-menu
            v-model="menu2"
            :close-on-content-click="false"
            :nudge-right="40"
            transition="scale-transition"
            offset-y
            min-width="290px"
      >
        <template v-slot:activator="{ on }">
          <v-text-field
            v-model="due"
            label="Due date"
            prepend-icon="mdi-calendar"
            readonly
            v-on="on"
          ></v-text-field>
        </template>
        <v-date-picker v-model="due" @input="menu2 = false"></v-date-picker>
      </v-menu>

          <v-btn text @click="submit" class="success mx-0 mt-3">Add Project</v-btn>
        </v-form>
      </v-card-text>

    </v-card>
  </v-dialog>
</template>

<script>

import format from 'date-fns/format'

export default {
  data() {
    return {
      title: '',
      content: '',
      due: null,
      menu2: false
    }
  },

    computed:{
        formattedDate(){
            return this.due ? format(this.due, 'yyyy-MM-dd') : '';
        },
    },

  methods: {
    submit() {
      console.log(this.title, this.content)
    }
  }
}
</script>