<template>
  <div :class="['text-tags', alignmentClass]">
    <div
      v-for="(tag, index) in tagsWithSeparator"
      :key="index"
      class="text-tags__tag"
    >
      <div>
        <v-icon v-if="tag.icon">{{ tag.icon }}</v-icon>
        <span>{{ tag.text }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TextTags",
  props: {
    tags: {
      type: Array,
      required: true,
    },
    alignment: {
      type: String,
      default: "left",
      validator: (value) => ["left", "justify"].includes(value),
    },
  },
  computed: {
    alignmentClass() {
      return {
        "text-tags--left": this.alignment === "left",
        "text-tags--spread": this.alignment === "spread",
        "text-tags--right": this.alignment === "right",
      };
    },
    tagsWithSeparator() {
      const separatorIcon = { text: "", icon: "mdi-circle-small" };
      return this.tags.reduce(
        (newTags, tag, index) =>
          index > 0 ? [...newTags, separatorIcon, tag] : [tag],
        []
      );
    },
  },
};
</script>

<style lang="scss">
.text-tags {
  display: flex;
  flex-wrap: nowrap;
  overflow: hidden;

  &--left {
    justify-content: flex-start;
  }

  &--spread {
    justify-content: space-between;
  }

  &--right {
    justify-content: flex-end;
  }

  &__tag {
    display: flex;
    justify-content: space-between;
    align-items: center;
    white-space: nowrap;
  }
}
</style>
