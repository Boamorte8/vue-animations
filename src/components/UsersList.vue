<template>
  <transition-group tag="ul" name="user-list">
    <li v-for="user in users" :key="user.id" @click="removeUser(user.id)">
      {{ user.name }}
    </li>
  </transition-group>
  <div>
    <input type="text" name="add" ref="userNameInput" />
    <button @click="addUser">Add User</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          id: 1,
          name: 'John Doe',
          age: 32,
        },
        {
          id: 2,
          name: 'Max Lee',
          age: 30,
        },
        {
          id: 3,
          name: 'Jane Sage',
          age: 31,
        },
        {
          id: 4,
          name: 'Kate Tue',
          age: 31,
        },
        {
          id: 5,
          name: 'Kelly Tyrion',
          age: 31,
        },
      ],
    };
  },
  methods: {
    addUser() {
      const input = this.$refs.userNameInput;
      const name = input.value;
      input.value = '';
      this.users.unshift({
        id: this.users.length + 1,
        name,
        age: 30,
      });
    },
    removeUser(id) {
      this.users = this.users.filter(user => user.id !== id);
    },
  },
}
</script>

<style scoped>
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  border: 1px solid #ccc;
  padding: 1rem;
  text-align: center;
}

.user-list-enter-from {
  opacity: 0;
  transform: translateX(-30px);
}

.user-list-enter-active {
  transition: all 1s ease-out;
}

.user-list-enter-to {
  opacity: 1;
  transform: translateX(0);
}

.user-list-leave-from {
  opacity: 1;
  transform: translateX(0);
}

.user-list-leave-active {
  transition: all 1s ease-in;
  position: absolute;
}

.user-list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.user-list-move {
  transition: transform 1s ease;
}
</style>