<template>
  <div id="app">
    <h1>Order Monitoring</h1>

    <table>
      <thead>
        <tr>
          <th>Order ID</th>
          <th>Status</th>
          <th>Assignee</th>
          <th>Category</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="order in orders" :key="order.id">
          <td>{{ order.id }}</td>
          <td>
            <select v-model="order.status" style="width: 100px">
              <option v-for="status in statuses" :key="status" :value="status">
                {{ status }}
              </option>
            </select>
          </td>
          <td>
            <select v-model="order.assignee" style="width: 100px">
              <option v-for="assignee in assignees" :key="assignee" :value="assignee">
                {{ assignee }}
              </option>
            </select>
          </td>
          <td>{{ order.category }}</td>
          <td>
            <!-- Removed the Mark as Shipped button since status can be changed via dropdown -->
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "OrderMonitoringApp",
  data() {
    return {
      orders: [
        { id: 1, status: "pending", assignee: "John", category: "Clothing & Jewelry" },
        { id: 2, status: "pending", assignee: "Jane", category: "Clothing & Jewelry" },
        { id: 3, status: "pending", assignee: "Alex", category: "Clothing & Jewelry" },
        { id: 4, status: "pending", assignee: "Emma", category: "Clothing & Jewelry" },
        { id: 5, status: "pending", assignee: "Tom", category: "Clothing & Jewelry" },
        { id: 6, status: "pending", assignee: "Lucy", category: "Clothing & Jewelry" },
        { id: 7, status: "pending", assignee: "Mark", category: "Clothing & Jewelry" },
        { id: 8, status: "pending", assignee: "Sophia", category: "Clothing & Jewelry" },
        { id: 9, status: "pending", assignee: "Liam", category: "Clothing & Jewelry" },
        { id: 10, status: "pending", assignee: "Mia", category: "Clothing & Jewelry" },
      ],
      statuses: ["pending", "shipped", "delivered", "cancelled"],
      assignees: ["John", "Jane", "Alex", "Emma", "Tom", "Lucy", "Mark", "Sophia", "Liam", "Mia"]
    };
  }
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 0;
  padding: 0;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  width: 100%;
  min-height: 100vh;
  background-color: #f9f9f9;
  background-image: linear-gradient(to bottom, #f9f9f9, #fff);
}

header {
  background-color: #333;
  color: #fff;
  padding: 20px;
  text-align: center;
  border-radius: 10px 10px 0 0;
  width: 100%;
}

header h1 {
  margin: 0;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  width: 100%;
  background-color: #fff;
  border-radius: 0 0 10px 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

table {
  width: 100%;
  border-collapse: collapse;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

th, td {
  border: 1px solid #ddd;
  padding: 10px;
  text-align: left;
}

th {
  background-color: #f4f4f4;
}

td select {
  width: 100%;
  padding: 5px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

button {
  padding: 10px 20px;
  border: none;
  background-color: #007bff;
  color: #fff;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #0056b3;
}

button:disabled {
  background-color: #ddd;
  cursor: not-allowed;
}


</style>