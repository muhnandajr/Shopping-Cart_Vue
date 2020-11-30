<template>
    <div>
        <h3 style=color:DarkSlateBlue;>Shopping Cart using IoT </h3>
        <h3 style=color:DarkSlateBlue;>Your trolly is here! </h3>
        <br><br>
    <div class="container mb-4">
        <div class="row">
            <div class="col-md-12">
                <table class="table table-striped">
                    <thead>
                        <tr>
                            <th> </th>
                            <th scope="col" style="color:DarkSlateBlue">Items</th>
                            <th scope="col" style="color:DarkSlateBlue">Quantity</th>
                            <th scope="col" style="color:DarkSlateBlue">Price</th>
                            <th> </th>
                        </tr>
                    </thead>
                    
                      <tr>
                        <td></td>
                        <td style="color:DarkSlateBlue">Indomie</td>
                        <td style="color:DarkSlateBlue">2</td>
                        <td style="color:DarkSlateBlue">5.000</td>
                        <td></td>
                      </tr>
                      <tr>
                        <td></td>
                        <td style="color:DarkSlateBlue">Aqua</td>
                        <td style="color:DarkSlateBlue">1</td>
                        <td style="color:DarkSlateBlue">2.500</td>
                        <td></td>
                      </tr>
                      <tr>
                        <td></td>
                        <td style="color:DarkSlateBlue">Tricks</td>
                        <td style="color:DarkSlateBlue">2</td>
                        <td style="color:DarkSlateBlue">2.000</td>
                        <td></td>
                      </tr>
                      <thead>
                      <tr>
                        <th></th>
                        <th style="color:DarkSlateBlue">Total</th>
                        <th style="color:DarkSlateBlue">6</th>
                        <th style="color:DarkSlateBlue">9.500</th>
                        <th></th>
                      </tr>
                      </thead>
                    
                    <!-- <template slot-scope="{row}">
                        <th scope="row">
                            <div class="media-body text-md-center">
                            <span class="name mb-0 text-sm">{{row.id}}</span>
                            </div>
                        </th>
                        <th scope="row">
                            <div class="media-body">
                            <span class="name mb-0 text-sm">{{row.name}}</span>
                            </div>
                        </th>
                        <th scope="row">
                            <div class="media-body text-md-center">
                            <span class="name mb-0 text-sm">{{row.address}}</span>
                            </div>
                        </th>
                    </template> -->
                </table>
        </div>
    </div>
          <span style="float: right">
            <div class="add">
              <b-button :pressed="true" variant="primary">Add Promo</b-button>
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
// import CompanyDataService from "../../services/CompanyDataService";

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
      },
        tableData: 
        [{
            
          }],
          title_search:''
      }
    },
//     methods: {
//     retrieveCompany() {
//       CompanyDataService.getAll()
//         .then(response => {
//           this.tableData = response.data;
//           console.log(response.data);
//         })
//         .catch(e => {
//           console.log(e);
//         });
//     },
//   },
//     mounted() {
//     this.retrieveCompany();
//   }
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