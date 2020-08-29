<template #thead>
          <vs-tr>
            <vs-th>
              <vs-checkbox
                :indeterminate="selected.length == users.length" v-model="allCheck"
                @change="selected = $vs.checkAll(selected, users)"
              />
            </vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'name')">
              Name
            </vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'email')">
              Email
            </vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'id')">
              Id
            </vs-th>
          </vs-tr>
        </template>