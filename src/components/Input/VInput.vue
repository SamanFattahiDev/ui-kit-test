<!-- CustomInput.vue -->
<template>
  <div class="w-full">
    <span v-if="HaveLabel" class="pr-3 " for="">{{ PlaceHolder }}</span>
    <input
        :class="{'border border-green-600':IsRequired&&DataString.length===0}"
        :maxlength="LimitLength"
        :placeholder="!DisablePlaceHolder?PlaceHolder:''"
        :type="type"
        :value="DataString"
        class="rounded-full   my-3 bg-stone-100 focus:outline-none p-2  dark:text-black w-full  leading-6 "
        @input="$emit('input',$event.target.value)"
        @keydown.enter="$emit('EnterEvent')"
    >
    <div v-if="LimitLength" class="flex items-center gap-1 pr-3 ">
      <small>{{ DataString.length }}</small>
      <small>/</small>
      <small>{{ LimitLength }}</small>
    </div>
  </div>

</template>

<script>
export default {
  name:'VInput',
  props: {
    DataString: {
      type: String | Number,
      required: true
    },
    LimitLength: {
      type: Number,
      required: false
    },
    DisablePlaceHolder: {
      type: Boolean,
      required: false,
      default: false
    },
    type: {
      type: String,
      required: false,
      default: 'text'
    },
    PlaceHolder: {
      type: String,
      required: false
    },
    HaveLabel: {
      type: Boolean,
      required: false
    },
    IsRequired: {
      type: Boolean,
      required: false
    }
  },
  model: {
    prop: 'DataString',
    event: 'input'
  },
}
</script>

