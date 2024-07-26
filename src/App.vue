<template>
  <v-app>
    <v-container style="max-width: 100%">
      <v-row>
        <v-col class="mt-3"
          ><h4>
            Компонент на всю ширину экрана с выравниванием по левому краю
          </h4></v-col
        >
        <v-col cols="12" style="border: 1px solid black">
          <TextTags :tags="tags" alignment="left" />
        </v-col>
      </v-row>
      <v-row>
        <v-col class="mt-2"
          ><h4>
            Компонент на всю ширину экрана с выравниванием по ширине
          </h4></v-col
        >
        <v-col cols="12" style="border: 1px solid black">
          <TextTags :tags="tags" alignment="spread" />
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="6" class="mt-3"
          ><h4>
            Компонент на 50% ширины экрана с выравниванием по левому краю
          </h4></v-col
        >
        <v-col cols="6" class="mt-3"
          ><h4>
            Компонент на 50% ширины экрана с выравниванием по ширине
          </h4></v-col
        >
        <v-col cols="6" style="border: 1px solid black">
          <TextTags :tags="tags" alignment="left" />
        </v-col>
        <v-col cols="6" style="border: 1px solid black">
          <TextTags :tags="tags" alignment="spread" />
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import TextTags from "./components/TextTags.vue";

export default {
  name: "App",
  components: {
    TextTags,
  },
  data() {
    return {
      tags: [
        { text: "текст1" },
        { text: "текст2", icon: "mdi-guitar-acoustic" },
        { text: "длиииииинный текст3" },
        { text: "текст4", icon: "mdi-bell" },
        { text: "текст5", icon: "mdi-bugle" },
        // { text: "текст6" },
        // { text: "текст7", icon: "mdi-saxophone" },
      ],
    };
  },
};
</script>

<style></style>
