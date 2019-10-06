<template>
  <v-app>
    <v-content>
      <v-autocomplete label="Simple List" :items="components"></v-autocomplete>
      <v-autocomplete label="Array Of Objects" :items="array" :item-text="name" :item-value="name">
        <template v-slot:selection="data">
          <v-chip
            v-bind="data.attrs"
            :input-value="data.selected"
            close
            @click="data.select"
            @click:close="remove(data.item)"
          >{{ data.item.name }}</v-chip>
        </template>

        <template v-slot:item="{ item }">
          <v-list-item-avatar
            color="indigo"
            class="headline font-weight-light white--text"
          >{{ item.name.charAt(0) }}</v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title v-text="item.name"></v-list-item-title>
            <v-list-item-subtitle v-text="item.symbol"></v-list-item-subtitle>
          </v-list-item-content>
          <v-list-item-action>
            <v-icon>mdi-coin</v-icon>
          </v-list-item-action>
        </template>
      </v-autocomplete>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      array: [
        {
          name: "test name",
          type: "dragon",
          likes: "carrots",
          symbol: "DARGON"
        }
      ],

      components: [
        "Autocompletes",
        "Comboboxes",
        "Forms",
        "Inputs",
        "Overflow Buttons",
        "Selects",
        "Selection Controls",
        "Sliders",
        "Textareas",
        "Text Fields"
      ]
    };
  }
};
</script>
