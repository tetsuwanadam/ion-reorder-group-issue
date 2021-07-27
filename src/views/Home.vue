<!--
ion-item-group issue reproduction
Issues:
1. On touch devices, swiping up or down an item wrapped in ion-reorder immediately reorders the item, preventing page scroll
2. ion-item-sliding doesn't work if it contains an item wrapped in ion-reorder (Item 3)
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
        <ion-reorder-group disabled="false">
          <ion-reorder>
            <ion-item>
              <ion-label>
                Item 1 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label>
                Item 2 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-item-sliding>
            <ion-reorder>
              <ion-item>
                <ion-label>
                  Item 3 (the whole item can be dragged, with ion-item-sliding)
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
              <ion-label>
                Item 4 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label>
                Item 5 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label>
                Item 6 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>

          <ion-reorder>
            <ion-item>
              <ion-label>
                Item 7 (the whole item can be dragged)
              </ion-label>
            </ion-item>
          </ion-reorder>
        </ion-reorder-group>
      </ion-list>

      <div style="height: 80vh; padding: 30px 15px; background: #eee;">
        ion-reorder-group's disabled attribute is set to false.
        <br><br>
        The rest of this is filler content to make sure page is long enough to scroll.
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
});
</script>
