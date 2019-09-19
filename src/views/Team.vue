<template>
  <div>
    <v-subheader>Team</v-subheader>

    <v-container class="my-5">
        <v-row wrap>
          <v-col v-for="person in team" :key="person.name">
            <v-card  class="pa-3 text-center" width="200">
              <v-avatar size="100" class="grey lighten-2">
                <v-img :src="person.avatar"/>
              </v-avatar>
              
              <v-card-text>
                <v-subheader>{{ person.name }}</v-subheader>
                <div class="grey--text">
                  {{ person.role }}
                </div>
              </v-card-text>

              <v-card-actions>
                <v-btn text color="grey">
                  <v-icon small left>mdi-message</v-icon>
                  <span>message</span>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
    </v-container>

  </div>
</template>

<script>

export default {
  data() {
      return {
        team: [
          { name: 'The Net Ninja', role: 'Web developer', avatar:'https://api.adorable.io/avatars/188/abott@adorable.png' },
          { name: 'Ryu', role: 'Graphic designer', avatar:'https://api.adorable.io/avatars/188/abott@adorable.png' },
          { name: 'Chun Li', role: 'Web developer', avatar:'https://api.adorable.io/avatars/188/abott@adorable.png' },
          { name: 'Gouken', role: 'Social media maverick', avatar:'https://api.adorable.io/avatars/188/abott@adorable.png' },
          { name: 'Yoshi', role: 'Sales guru', avatar:'https://api.adorable.io/avatars/188/abott@adorable.png'}
        ]
      }
    }
};
</script>
