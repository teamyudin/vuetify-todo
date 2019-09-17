<template>
    <nav>
        <v-toolbar flat app>

            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Todo</span>
                <span>App</span>
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn text>
                Sign Out
                <v-icon right>mdi-exit-to-app</v-icon>
            </v-btn>

        </v-toolbar>
    </nav>
</template>

<script>

export default {
  components: {
  },
};
</script>
