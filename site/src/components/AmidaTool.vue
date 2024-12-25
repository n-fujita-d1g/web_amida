<template>
  <div class="mt-4">
    <v-row class="align-center" no-gutters>
      <v-col cols="5">
        <v-textarea label="ゴール選択肢" variant="outlined" v-model="entries"></v-textarea>
      </v-col>
      <v-col cols="2" class="text-center">
        <v-btn color="info" append-icon="mdi-chevron-right" size="large">追加</v-btn>
      </v-col>
      <v-col cols="5">
        <v-badge :content="items.length"></v-badge>
        <v-card class="ma-2">
          <v-list :items="items"></v-list>
        </v-card>
      </v-col>
    </v-row>
    <v-row no-gutters>
      <v-col cols="7">
        <ul class="notation text-red text-caption">
          <li>ゴール選択肢を改行で区切って入力してください。</li>
          <li>空行、空白のみの行は追加されません。</li>
          <li>既存の選択肢に追加されます。</li>
        </ul>
      </v-col>
      <v-col>
        <v-row>
          <v-col>
            <v-btn block color="error" size="large" variant="outlined">削除</v-btn>
          </v-col>
          <v-col>
            <v-btn block color="info" size="large">クリア</v-btn>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-btn block color="primary" size="x-large">作成</v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'

const entries = ref<string>('')

const items = computed(() => {
  return [
    { title: '選択肢1', value: 1 },
    { title: '選択肢2', value: 2 },
    { title: '選択肢3', value: 3 },
  ]
})
</script>

<style lang="scss" scoped>
.notation {
  list-style-type: '※';
  margin-left: 1em;
}
</style>
