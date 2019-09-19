<template>
    <nav>
        <v-navigation-drawer v-model="drawer" app clipped>

            <v-layout column align-center>
                <v-avatar size="100" > 
                    <img class="text-lg-center" src="https://api.adorable.io/avatars/188/abott@adorable.png'">
                </v-avatar>

                <v-subheader>Dmitry Yudin</v-subheader>
            </v-layout>

            <v-list class="pt-0">
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                    <v-list-item-icon>
                        <v-icon>{{ link.icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title>{{ link.text }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>

        <v-app-bar app flat clipped-left>

            <v-app-bar-nav-icon class="grey--text" @click="drawer =! drawer"/>

            <router-link to="/" class="toolbar-title" tag="span" :style="{ cursor: 'pointer'}">
                <v-toolbar-title class="text-uppercase grey--text" to="/" router>
                    <span class="font-weight-light">Todo</span>
                    <span>App</span>
                </v-toolbar-title>
            </router-link>
            
            <v-spacer></v-spacer>

            <v-menu offset-y>
                <template v-slot:activator="{ on }">
                    <v-btn text v-on="on">
                        <v-icon left>mdi-chevron-down</v-icon>
                        <span>Menu</span>
                    </v-btn>
                </template>
                <v-list>
                    <v-list-item
                    v-for="link in links"
                    :key="link.text"
                    router :to="link.route"
                    >
                    <v-list-item-title >{{ link.text }}</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>

            <v-btn text>
                Sign Out
                <v-icon right>mdi-exit-to-app</v-icon>
            </v-btn>

        </v-app-bar>
    </nav>
</template>

<script>

export default {
    data() {
        return {
            drawer: true,
            links: [
                    { icon: 'mdi-view-dashboard', text: 'Dashboard', route: '/' },
                    { icon: 'mdi-folder', text: 'My Projects', route: '/projects' },
                    { icon: 'mdi-account', text: 'Team', route: '/team' },
                ],         
        }
    },
    components: {
    },
};
</script>
