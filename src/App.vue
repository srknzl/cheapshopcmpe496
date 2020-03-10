<template>
  <div id="app">
    <b-container class="cheapShopForm">
      <b-row>
        <b-col cols="9" align-h="start" class="p-0 title">
          <p class="whiteText">Cheap Shop Catalog Store</p>
        </b-col>
        <b-col cols="1" class="p-0">
          <b-button variant="light" class="m-0 borderRadiusZero">_</b-button>
        </b-col>
        <b-col cols="1" class="p-0">
          <b-button variant="light" class="m-0 borderRadiusZero">□</b-button>
        </b-col>
        <b-col cols="1" class="p-0">
          <b-button variant="light" class="m-0 borderRadiusZero">x</b-button>
        </b-col>
      </b-row>
      <b-row v-if="!hidePurchase">
        <b-col>
          <p class="thickBig">Purchaser</p>
        </b-col>
      </b-row>
      <b-row v-if="!hidePurchase" class="border-3">
        <b-col>
          <b-row>
            <b-col>
              <b-form-group id="input-group-13" label="Name: " label-for="input-1">
                <b-form-input id="input-1" v-model="form.name" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col>
              <b-form-group id="input-group-12" label="Phone: " label-for="input-2"></b-form-group>
              <b-form-input id="input-2" v-model="form.phone" required></b-form-input>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-form-group id="input-group-11" label="Postal Code: " label-for="input-3"></b-form-group>
              <b-form-input id="input-3" v-model="form.postalCode" required></b-form-input>
            </b-col>
            <b-col>
              <b-form-group id="input-group-10" label="Province: " label-for="input-4"></b-form-group>
              <b-form-input id="input-4" v-model="form.province" required></b-form-input>
            </b-col>
            <b-col>
              <b-form-group id="input-group-9" label="City: " label-for="input-5">
                <b-form-input id="input-5" v-model="form.city" required></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-form-group id="input-group-8" label="Delivery Address: " label-for="input-9">
                <b-form-input id="input-9" v-model="form.deliveryAddress" required></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-form-group id="input-group-7" label="Today's Date: " label-for="input-7">
                <b-form-input id="input-7" v-model="form.todaysDate" required type="date"></b-form-input>
              </b-form-group>
            </b-col>
            <b-col></b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-form-group id="input-group-7" label="Credit Card No: " label-for="input-8">
                <b-form-input id="input-8" v-model="form.creditCardNo" required></b-form-input>
              </b-form-group>
            </b-col>
            <b-col>
              <b-form-group
                id="input-group-6"
                label="for dept use: validation id: "
                label-for="input-15"
              >
                <b-form-input class="small" id="input-15" v-model="form.validationId" required></b-form-input>
              </b-form-group>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <p class="thickBig">Catalog Item</p>
        </b-col>
      </b-row>
      <b-row class="border-3 mt-1">
        <b-col>
          <b-form-group id="input-group-4" label="Number: " label-for="input-10">
            <b-form-input id="input-10" v-model="form.number" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col>
          <b-form-group id="input-group-3" label="Quantity: " label-for="input-11">
            <b-form-input id="input-11" v-model="form.quantity" required type="number"></b-form-input>
          </b-form-group>
        </b-col>
        <b-col>
          <b-form-group id="input-group-5" label="Cost/Item: " label-for="input-12">
            <b-form-input id="input-12" v-model="form.costPerItem" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col>
          <b-form-group id="input-group-2" label="Total: " label-for="input-13">
            <b-form-input id="input-13" v-model="form.total" required></b-form-input>
          </b-form-group>
        </b-col>
      </b-row>
      <b-row class="mt-1 border-3" align-v="center">
        <b-col>
          <b-form-group id="input-group-1" label-for="input-14" label="Balance Owing: ">
            <b-form-input id="input-14" v-model="form.balanceOwing" required></b-form-input>
          </b-form-group>
        </b-col>
        <b-col>
          <b-row>
            <b-col>
              <b-button @click="hidePurc">Next Catalog Item (PF5)</b-button>
            </b-col>
          </b-row>
          <b-row class="mt-1">
            <b-col>
              <b-button>Trigger Invoice (PF8)</b-button>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data: function() {
    return {
      form: {
        name: "",
        phone: "",
        postalCode: "",
        province: "",
        city: "",
        deliveryAddress: "",
        todaysDate: "",
        creditCardNo: "",
        validationId: "",
        number: "",
        quantity: "",
        costPerItem: "",
        total: "",
        balanceOwing: ""
      },
      hidePurchase: false
    };
  },
  methods: {
    hidePurc() {
      this.hidePurchase = true;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 30rem;
  max-height: 30rem;
}
body {
  display: flex;
  justify-content: center;
  align-items: center;
}
.title {
  background-color: black;
}
.borderRadiusZero {
  border-radius: 0px !important;
}
.whiteText {
  color: white;
}
.cheapShopForm {
  background-color: #a8a7a8;
  border: 3px solid black;
}
label {
  color: white;
}
.border-3 {
  border: 3px solid black !important;
}
.thickBig {
  font-size: 2rem;
  color: black;
  font-weight: bolder;
}
.small {
  max-width: 3rem;
}
</style>
