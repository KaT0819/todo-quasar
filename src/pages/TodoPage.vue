<template>
  <q-page class="bg-grey-3 column">
    <div class="row q-pa-sm bg-primary">
      <q-input
        v-model="newTask"
        @keyup.enter="addTask"
        class="col"
        square
        filled
        placeholder="タスクを追加する"
        bg-color="white"
        dense
      >
        <template v-slot:append>
          <q-btn @click="addTask" round dense flat icon="add" />
        </template>
      </q-input>
    </div>
    <q-list class="bg-white" separator bordered>
      <q-item
        v-for="(task, index) in tasks"
        :key="task.title"
        @click="task.done = !task.done"
        :class="{ 'done bg-blue-1': task.done }"
        clickable
        v-ripple
      >
        <q-item-section avatar>
          <q-checkbox
            v-model="task.done"
            class="no-pointer-events"
            color="primary"
          />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
        <q-item-section v-if="task.done" side>
          <q-btn
            @click.stop="deleteTask(index)"
            flat
            round
            dense
            color="primary"
            icon="delete"
          ></q-btn>
        </q-item-section>
      </q-item>
    </q-list>
    <div v-if="!tasks.length" class="no-tasks absolute-center">
      <q-icon name="check" size="100px" color="primary" />
      <div class="text-h5 text-primary text-center">No tasks</div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { useQuasar } from 'quasar';
import { Console } from 'console';

export default {
  data() {
    return {
      newTask: '',
      tasks: [
        // {
        //   title: 'Get bananas',
        //   done: false,
        // },
        // {
        //   title: 'Eat bananas',
        //   done: true,
        // },
        // {
        //   title: 'Poo bananas',
        //   done: false,
        // },
      ],
    };
  },
  methods: {
    deleteTask(index: number) {
      // const $q = useQuasar();

      this.$q
        .dialog({
          title: '確認',
          message: '削除しますか？',
          cancel: true,
          persistent: true,
          // dark: true,
        })
        .onOk(() => {
          this.tasks.splice(index, 1);
          this.$q.notify('タスクを削除しました');
        });
      console.log('del task');
    },
    addTask() {
      console.log('add task');
      this.tasks.push({
        title: this.newTask,
        done: false,
      });
      this.newTask = '';
    },
  },

  setUp() {
    return {
      confirm: ref(false),
    };
  },
};
</script>

<style lang="scss">
.done {
  .q-item__label {
    text-decoration: line-through;
    color: #bbb;
  }
}
.no-tasks {
  opacity: 0.5;
}
</style>
