<template>
  <div>
    <div id="burger-table">
      <OrderMessage :message="msg" v-show="msg" />
      <div>
        <div id="burger-table-heading">
          <div class="order-id">#:</div>
          <div>Cliente:</div>
          <div>Pão:</div>
          <div>Carne:</div>
          <div>Opcionais:</div>
          <div>Ações:</div>
        </div>
        <div id="burger-table-rows">
          <div
            class="burger-table-row"
            v-for="burger in burgers"
            :key="burger.id"
          >
            <div class="order-number">{{ burger.id }}</div>
            <div>{{ burger.nome }}</div>
            <div>{{ burger.pao }}</div>
            <div>{{ burger.carne }}</div>
            <div>
              <ul>
                <li v-for="(opcional, index) in burger.opcionais" :key="index">
                  <!-- Utilizando index pois não existe ID nos opcionais -->
                  {{ opcional }}
                </li>
              </ul>
            </div>
            <div>
              <select
                name="status"
                class="status"
                @change="updateBurger($event, burger.id)"
              >
                <option
                  :value="s.tipo"
                  v-for="s in status"
                  :key="s.id"
                  :selected="burger.status == s.tipo"
                >
                  {{ s.tipo }}
                </option>
              </select>
              <button class="delete-btn" @click="deleteBurger(burger.id)">
                Cancelar
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import OrderMessage from "./OrderMessage.vue";
export default {
  name: "OrderDashboard",
  data() {
    return {
      burgers: null,
      burger_id: null,
      status: [],
      msg: null,
    };
  },
  methods: {
    async getOrders() {
      const req = await fetch("http://localhost:3000/burgers");
      const data = await req.json();
      this.burgers = data;
      console.log(this.burgers);
      this.getStatus();
    },
    async getStatus() {
      const req = await fetch("http://localhost:3000/status");
      const data = await req.json();
      this.status = data;
    },

    async deleteBurger(id) {
      const req = await fetch(`http://localhost:3000/burgers/${id}`, {
        method: "DELETE",
        // Interpolando o id do pedido para ser deletado
      });
      const res = await req.json();
      this.msg = `Pedido removido com sucesso!`;
      console.log(res);
      setTimeout(() => {
        this.msg = null;
      }, 3000);
      this.getOrders();
    },

    async updateBurger(event, id) {
      const option = event.target.value;
      const dataJson = JSON.stringify({ status: option });
      const req = await fetch(`http://localhost:3000/burgers/${id}`, {
        method: "PATCH",
        headers: {
          "Content-Type": "application/json",
        },
        body: dataJson,
      });
      const res = await req.json();
      this.msg = `Status do pedido ${res.id} atualizado para ${res.status}.`;
      console.log(res);
      setTimeout(() => {
        this.msg = null;
      }, 3000);
    },
  },
  mounted() {
    this.getOrders();
  },
  components: {
    OrderMessage,
  },
};
</script>

<style scoped>
#burger-table {
  max-width: 1200px;
  margin: 0 auto;
}

#burger-table-heading,
#burger-table-rows,
.burger-table-row {
  display: flex;
  flex-wrap: wrap;
}

#burger-table-heading {
  font-weight: bold;
  padding: 12px;
  border-bottom: 3px solid #333;
}

#burger-table-heading div,
.burger-table-row div {
  width: 19%;
}

.burger-table-row {
  width: 100%;
  padding: 12px;
  border-bottom: 1px solid #ccc;
}

#burger-table-heading .order-id,
.burger-table-row .order-number {
  width: 5%;
}

select {
  padding: 12px 6px;
  margin-right: 12px;
}

.delete-btn {
  background-color: #222;
  color: #fcba02;
  font-weight: bold;
  border: 2px solid #222;
  padding: 10px;
  font-size: 16px;
  margin: 0 auto;
  cursor: pointer;
  transition: 0.5s;
}

.delete-btn:hover {
  background-color: transparent;
  color: #222;
}
</style>
