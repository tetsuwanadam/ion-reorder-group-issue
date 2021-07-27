<!--
ion-item-group issue reproduction
-->

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Reorder</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content id="content">
      <ion-list>
        <ion-reorder-group disabled="false" @ionItemReorder="doReorder($event)">
          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 1 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 2 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-item-sliding>
            <ion-reorder>
              <ion-item>
                <ion-label class="ion-text-wrap">
                  Item 3 (the whole item can be dragged, inside ion-item-sliding)
                </ion-label>
              </ion-item>
            </ion-reorder>

            <ion-item-options side="start">
              <ion-item-option>Favorite</ion-item-option>
              <ion-item-option color="danger">Share</ion-item-option>
            </ion-item-options>

            <ion-item-options side="end">
              <ion-item-option>Unread</ion-item-option>
            </ion-item-options>
          </ion-item-sliding>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 4 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 5 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 6 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 7 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 8 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 9 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label class="ion-text-wrap">
                Item 10 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>
        </ion-reorder-group>
      </ion-list>

      <div style="height: 80vh; padding: 30px 15px; background: #eee;">
        ion-reorder-group's disabled attribute is set to false.
        <br>
        <br>Issues:
        <br>1. On touch devices, swiping up or down on an item wrapped in ion-reorder reorders the item, which prevents you from being able to scroll the page. (Specifying to reorder only after a long press would solve this.)
        <br>2. ion-item-sliding doesn't work if it contains an item wrapped in ion-reorder (Item 3).
        <br>
        <br>The rest of this div is filler to make sure page is long enough to scroll.
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonItem, IonItemOption, IonItemOptions, IonItemSliding, IonLabel, IonReorder, IonReorderGroup, IonTitle, IonToolbar } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonItem,
    IonItemOption,
    IonItemOptions,
    IonItemSliding,
    IonLabel,
    IonReorder,
    IonReorderGroup,
    IonTitle,
    IonToolbar
  },
  setup() {
    const doReorder = (event: CustomEvent) => {
      console.log('Dragged from index', event.detail.from, 'to', event.detail.to);
      event.detail.complete();
    }
    return { doReorder }
  }
});
</script>

<style scoped>
ion-item {
  --inner-padding-bottom: 10px;
  --inner-padding-top: 10px;
}
</style>