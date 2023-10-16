<template>
  <Page>
    <ActionBar>
      <Label text="This is Takumi's app"/>
    </ActionBar>

    <StackLayout>
      <Label textWrap="true"> 
        <FormattedString>
          <Span :text="message"></Span>
          <Span text="\nAlso a really cool message"></Span>
        </FormattedString>
      </Label>
      <Image src="https://art.nativescript-vue.org/NativeScript-Vue-White-Green.png" stretch="none" />
      <Label textWrap="true"> 
        <FormattedString>
          <Span :text="numValue"></Span>
        </FormattedString>
      </Label>
      <FlexboxLayout>
        <Button text="Add 1" @tap="onAddUp" />
        <Button text="Subtract 1" @tap="onSubtractDown" />
      </FlexboxLayout>
      <FlexboxLayout>
        <Label textWrap="true"> 
          <FormattedString>
            <Span :text="listOfItems[selectedItem]"></Span>
          </FormattedString>
        </Label>
        <ListPicker :items="listOfItems" v-model="selectedItem"/>
      </FlexboxLayout>
    </StackLayout>
    
    
  </Page>
</template>

<script lang="ts">
import { FlexboxLayout, GridLayout } from "@nativescript/core";
import Vue from "nativescript-vue";

  export default Vue.extend({
    data() {
        return {
            numValue: 0,
            listOfItems: ["Item 1", "Item 2", "Item 3"],
            selectedItem: 0,
        };
    },
    computed: {
        message() {
            return "Hello World! My name is Takumi";
        },
    },
    methods: {
        onAddUp() {
            this.numValue += 1;
            alert('Number increased');
        },
        onSubtractDown() {
            this.numValue -= 1;
        }
    },
});
</script>

<style scoped lang="scss">
  @import '@nativescript/theme/scss/variables/blue';

  // Custom styles
</style>
