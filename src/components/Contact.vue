<template>
  <li class="contact-list-item">
    <div>
      Name: {{ contact.name }}
    </div>
    <div>
      Phone: {{ contact.phone | withoutHyphens }}
    </div>
  </li>
</template>

<script>
export default {
  filters: {
    withoutHyphens(value) {
      return value.replace(/-/g, "");
    }
  },
  props: {
    contact: {
      type: Object,
      required: true
    }
  }
};
</script>

<style>
.contact-list-item {
  display: flex;
  justify-content: center;
  flex-direction: column;
  height: 100px;
  border: 1px solid #dae1e7;
  border-left: 4px solid #4dc0b5;
  border-radius: 4px;
  padding: 10px 0;
  margin-bottom: 10px;
}
</style>
