<template>
  <div :class="groupType + '-group'">
    <label v-if="title" :for="vaId">{{ title }}</label>
    <div v-if="$slots.slotPrefixButton" class="input-group-btn">
      <slot name="slotPrefixButton"></slot>
      <slot name="slotPrefixDropdown"></slot>
    </div>
    <span v-if="prefixAddonText || $slots.slotPrefixAddonText" class="input-group-addon">
      {{ prefixAddonText }}
      <slot name="slotPrefixAddonText"></slot>
    </span>
    <va-input
        :type="type"
        :vaId="vaId"
        :placeholder="placeholder"
        :size="size"
        :value="value"
        :isFormControl="type!='file'"
    ></va-input>
    <span v-if="suffixAddonText || $slots.slotSuffixAddonText" class="input-group-addon">
      {{ suffixAddonText }}
      <slot name="slotSuffixAddonText"></slot>
    </span>
    <div v-if="$slots.slotSuffixButton" class="input-group-btn">
      <slot name="slotSuffixButton"></slot>
      <slot name="slotSuffixDropdown"></slot>
    </div>
    <p v-show="helpBlock" class="help-block">{{ helpBlock }}</p>
  </div>
</template>

<script>
import VAInput from './VAInput'
export default {
  name: 'va-input-group',
  props: {
    groupType: {
      type: String,
      default: 'form'
    },
    title: {
      type: String
    },
    type: {
      type: String,
      default: 'text'
    },
    vaId: {
      type: String
    },
    placeholder: {
      type: String,
      default: 'Enter Text...'
    },
    size: {
      type: String
    },
    value: {
      type: String
    },
    helpBlock: {
      type: String
    },
    prefixAddonText: {
      type: String
    },
    suffixAddonText: {
      type: String
    }
  },
  created () {

  },
  components: {
    'va-input': VAInput
  }
}
</script>
