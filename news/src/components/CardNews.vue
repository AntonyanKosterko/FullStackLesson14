<template>
  <v-card>
    <v-img
      src="https://picsum.photos/400"
      class="white--text align-end"
      gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
      height="200px"
    >
      <v-card-title v-text="loh"></v-card-title>
    </v-img>

    <v-card-text>
      <p>dkfljdfklkhdklgjdflkjgdfkgdffj</p>
    </v-card-text>

    <v-card-actions>
      <v-btn plain>
        <v-icon class="mr-1">mdi-link-variant</v-icon>
        source
      </v-btn>
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-bookmark</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-share-variant</v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>