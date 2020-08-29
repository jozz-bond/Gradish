<template>
  <div class="container" style="margin: auto; width: 900px">
    <div>
      <vs-table v-model="selected">
        <template #header>
          <vs-input v-model="search" border placeholder="Search" />
        </template>
        <template #thead>
          <vs-tr>
            <vs-th></vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Company')">Company</vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Role')">Job Title</vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Level')">Level</vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Location')">Location</vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Status')">Status</vs-th>
            <!-- <vs-th sort @click="users = $vs.sortData($event ,users, 'closingDate')">Id</vs-th> -->
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Process')">Process Rating</vs-th>
            <vs-th sort @click="users = $vs.sortData($event ,users, 'Desirability')">Desirability</vs-th>
          </vs-tr>
        </template>
        <template #tbody>
          <vs-tr
            :key="i"
            v-for="(tr, i) in $vs.getSearch(users, search)"
            :data="tr"
            not-click-selected
            :is-selected="!!selected.includes(tr)"
            open-expand-only-td
          >
            <vs-td></vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Company', editActive = true"
            >{{ tr.Company}}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Role', editActive = true"
            >{{ tr.Role }}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Level', editActive = true"
            >{{ tr.Level }}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Location', editActive = true"
            >{{ tr.Location }}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Status', editActive = true"
            >{{ tr.Status }}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Process', editActive = true"
            >{{ tr.Process }}</vs-td>
            <vs-td
              edit
              @click="edit = tr, editProp = 'Desirability', editActive = true"
            >{{ tr.Desirability }}</vs-td>
          </vs-tr>
        </template>
      </vs-table>

      <vs-dialog v-model="editActive">
        <template #header>Edit {{ editProp }}</template>
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Company'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Role'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Level'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Location'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Status'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress="editActive = false"
          v-if="editProp == 'Process'"
          v-model="edit[editProp]"
        />
        <vs-input
          @keypress.enter="editActive = false"
          v-if="editProp == 'Desirability'"
          v-model="edit[editProp]"
        />
      </vs-dialog>
    </div>
  </div>
</template>


<script>
export default {
  data: () => ({
    editActive: false,
    edit: null,
    editProp: {},
    search: "",
    allCheck: false,
    active: 0,
    selected: [],
    users: [
      {
        Company: "Canva",
        Role: "Product Design",
        Level: "Internship",
        Location: "Sydney",
        dateApplied: "23/07/2020",
        Status: "First round phone interview",
        closingDate: "23/08/2020",
        Process: "2",
        Desirability: "4",
      },
      {
        Company: "EY",
        Role: "UX Design",
        Level: "Internship",
        Location: "Melbourne",
        dateApplied: "20/07/2020",
        Status: "Second round phone interview",
        closingDate: "23/08/2020",
        Process: "5",
        Desirability: "4",
      },
      {
        Company: "Google",
        Role: "UI Design",
        Level: "Internship",
        Location: "Perth",
        dateApplied: "10/07/2020",
        Status: "Rejected",
        closingDate: "29/08/2020",
        Process: "2",
        Desirability: "5",
      },
      {
        Company: "Atlassian",
        Role: "Front-end Developer",
        Level: "Internship",
        Location: "Sydney",
        dateApplied: "5/07/2020",
        Status: "Online Assessment",
        closingDate: "9/08/2020",
        Process: "5",
        Desirability: "5",
      },
      
    ],
  }),
};
</script>


