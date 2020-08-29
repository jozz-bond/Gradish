  <template>
  <vs-navbar center-collapsed v-model="active">
    <template #left>gradish</template>
    <template #right>
      <vs-navbar-item :active="active == 'dashboard'" id="dashboard">Dashboard</vs-navbar-item>
      <vs-navbar-item :active="active == 'tracker'" id="tracker">My Tracker</vs-navbar-item>
      <vs-navbar-item :active="active == 'companies'" id="companies">Companies</vs-navbar-item>
      <vs-avatar circle size="32">
        <template #text>Margaux</template>
      </vs-avatar>
    </template>
  </vs-navbar>
</template>