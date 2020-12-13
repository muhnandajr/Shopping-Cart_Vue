<template>
    <div>
        <h3 style=color:DarkSlateBlue;>Shopping Cart using IoT </h3>
        <h3 style=color:DarkSlateBlue;>Your trolly is here! </h3>
        <br><br>
    <div class="container mb-4">
        <div class="row">
            <div class="col-md-12">
                         <div>
    <b-table striped hover :items="tableData" :fields="fields"></b-table>
          <strong><p align=right>Total Product: {{total_product}}    Total Price: {{total}}</p> </strong>


  </div>
        </div>
    </div>
          <span style="float: right">
            <div class="add">
              <b-button :pressed="true" variant="primary" @click="deleteCart">Add Promo</b-button>
            </div>
        
            <div class="pay">
              <b-button :pressed="true" variant="success">Pay Now</b-button>
            </div>
          </span>
  </div>
        <div class="footer">
          <p style="color:DarkGreen" align="center">© Shopping Cart Application powered by PMLD 2020</p>
        </div>
        
</div>
</template>



<script>
import CartDataService from "../services/CartDataService";

  export default {
    name: 'projects-table',
    props: {
      type: {
        type: String
      },
      title: String
    },
    data() {
      return {
        pagination: {
        default: 1
      },fields:['product_id','name','quantity','price'],
        tableData: 
        [{
            
          }],
          title_search:'',
      }
    },
    methods: {
    retrieveCart() {
      CartDataService.getAll()
        .then(response => {
          this.tableData = response.data;
          console.log(response.data);
        })
        .catch(e => {
          console.log(e);
        });
    },
     deleteCart() {
      CartDataService.deleteAll()
        .then(response => {
          console.log(response.data);
          // this.$router.push({ name: "topics" });
        })
        .catch(e => {
          console.log(e);
        });
    },
  },
    mounted() {
    this.retrieveCart();
    this.timer = setInterval(this.retrieveCart,200)
  },
  computed: {
  total: function(){
    console.log(this.tableData);
    return this.tableData.reduce(function(total, item){
      return total + item.price; 
    },0);
  },
  total_product: function(){
    console.log(this.tableData);
    return this.tableData.reduce(function(total_product, item){
      return total_product + item.quantity; 
    },0);
  },
}
}
</script>

<style>
.footer {
   position: fixed;
   left: 0;
   bottom: 0;
   width: 100%;
   color: white;
   text-align: center;
}
.add {
  padding: 15px 32px;
  float: right;
}
.pay {
  padding: 15px 32px;
  float: right;
}
</style>