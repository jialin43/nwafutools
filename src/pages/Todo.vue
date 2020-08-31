<template>
  <q-page class="bg-grey-3 column">
    <q-list class="bg-white" separator border>
      <!--
        Rendering a <label> tag (notice tag="label")
        so QCheckboxes will respond to clicks on QItems to
        change Toggle state.
      -->

      <q-item
      v-for="task in tasks"
      :key="task.title"
      @click="task.done=!task.done"
      :class="{'done bg-blue-1':task.done}"
      clickable
       v-ripple>
        <q-item-section avatar>
          <q-checkbox v-model="task.done"  color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{task.title}}</q-item-label>
        </q-item-section>
      </q-item>

    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'Todo',
  data () {
    return {
      tasks: [
        {
          title: 'Get bananas',
          done: false
        },
        {
          title: 'Eat bananas',
          done: false
        },
        {
          title: 'Buy bananas',
          done: false
        }
      ]
    }
  }
}
</script>
<style lang="scss">
  .done {
    .q-item__label {
      text-decoration: line-through;
      color:#bbb;
    }
  }
</style>
