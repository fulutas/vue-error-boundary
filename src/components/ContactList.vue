<template>
  <div>
    <h1>My Contacts</h1>
    <ul class="contact-list">
      <template v-for="contact in contacts">
        <div :key="contact.id">
          <ErrorBoundary :fall-back="fallBack" :key="contact.key">
            <AppContact :contact="contact"/>
          </ErrorBoundary>
        </div>
      </template>
    </ul>
  </div>
</template>

<script>
import { ErrorBoundary } from "vue-error-boundary";
import AppContact from "./Contact";
import ContactError from "./ContactError";

export default {
  name: "ContactList",
  components: {
    AppContact,
    ErrorBoundary
  },
  data: () => ({
    fallBack: ContactError,
    contacts: [
      { id: 1, name: "Edgar Degas", phone: "331-827-1917", key: 1 },
      { id: 2, name: "Leonardo da Vinci", phone: null, key: 2 },
      { id: 3, name: "Mary Cassatt", phone: "412-614-1926", key: 3 },
      { id: 4, name: "Bob Ross", phone: "907-704-1995", key: 4 },
      { id: 5, name: "Claude Monet", phone: "331-125-1926", key: 5 }
    ]
  })
};
</script>

<style scoped>
.contact-list {
  width: 300px;
  list-style: none;
  margin: 0 auto;
  padding: 0;
}
</style>
