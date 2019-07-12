<template>
	<div>
		<v-layout column wrap>
			<v-layout>
				<v-container>
					<v-layout row wrap>
						<v-card width="255px" height="96px" color="#009688" class='ma-3 elevation-12' >
							<v-icon class="white--text pa-1" size="42px">bar_chart</v-icon>
							<v-card-title primary-title class="right white--text title font-weight-bold" >
								TK 13000000
							</v-card-title>
								<v-card-text class="white--text title font-weight-light">
								Invoice Amount
								</v-card-text>
							
						</v-card>
						<v-card width="250px" height="96px" color="#F44336" class='ma-3 elevation-12'>
							<v-icon class="white--text pa-1" size="42px">thumbs_up_down</v-icon>
							<v-card-title primary-title class="right white--text title font-weight-bold">
								Tk 2500000
							</v-card-title>
							
								<v-card-text class="white--text title font-weight-light">
									Receive Amount
								</v-card-text>
						</v-card>
						<v-card width="250px" height="96px" color="#FF5722" class='ma-3 elevation-12'>
							<v-icon class="white--text pa-1" size="42px">local_grocery_store</v-icon>
							<v-card-title primary-title class="right white--text title font-weight-bold">
								Tk 2500000.00
							</v-card-title>
							
								<v-card-text class="white--text title font-weight-light">
									Total Expenses
								</v-card-text>
						</v-card>
						<v-card width="250px" height="96px" color="#4CAF50" class='ma-3 elevation-12'>
							<v-icon class="white--text pa-1" size="42px">monetization_on</v-icon>
							<v-card-title primary-title class="right white--text title font-weight-bold">
								Tk 2500000.60
							</v-card-title>
							
								<v-card-text class="white--text title font-weight-light">
									Total Due Amount
								</v-card-text>
						</v-card>
					</v-layout>

				</v-container>
				
			</v-layout>
			<v-layout row>
				<div class="small">
					<Linechart :chart-data="datacollection1"/>
				</div>
				<div class="small">
					<Barchart :chart-data="datacollection2"/>
				</div>
				<div class="small">
					<Linechart :chart-data="datacollection3"/>
				</div>
			</v-layout>
			<v-layout row>
				
				<v-container>
					<Barchart :chart-data="datacollection4"/>
				</v-container>
					
			
			</v-layout>
		</v-layout>
	</div>
</template>

<script>
import Linechart from '../Linechart'
import Barchart from '../barchart'
  export default {

	components:{
		Linechart,
		Barchart
	},

    data: () => ({
		datacollection1:null,    
		datacollection2:null,    
		datacollection3:null,    
		datacollection4:null    
	}),
	mounted(){
		this.fillData()
	},
	methods:{
		fillData(){
			this.datacollection1={
				
      labels:['Jan','Feb','Mar','Apr','May','June','Juluy'],
      datasets:[
        {label:'Sales', backgroundColor: "#ff8a80", data: [40,20,29,10,22,50,20] },
        
      ]
			},
			this.datacollection2={
				
      labels:['Jan','Feb','Mar','Apr','May','June','Juluy'],
      datasets:[
        {label:'Recieve Amount', backgroundColor: "#ffb74d", data: [40,20,29,10,22,50,20] },
        
      ]
			}
			this.datacollection3={
				
      labels:['Jan','Feb','Mar','Apr','May','June','Juluy'],
      datasets:[
        {label:'Expenses Amount', backgroundColor: "#ff8a80", data: [40,20,29,10,22,50,20] },
        
      ]
			}
			this.datacollection4={
				
      labels:['Jan','Feb','Mar','Apr','May','June','Juluy'],
      datasets:[
        {label:'Recieve Amount', backgroundColor: "#ffb74d", data: [40,20,29,10,22,50,20] },
        {label:'Expense Amount', backgroundColor: "#ff8a80", data: [40,20,29,10,22,50,20] },
        
      ]
			}
		}
	}
  }
</script>

<style scoped>
.small{
	max-width: 50%;
    margin: auto;
}

</style>
