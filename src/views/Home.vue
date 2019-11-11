<template>
  <div class="home">
    <h1>Welcome To The Love Clinic ! </h1>
    <p>by <a style="color:white; !important" href="https://github.com/kaythinks">@Kaythinks</a> <span> --- on Github</span></p>
    <h3>It's {{this.$moment().format('dddd, MMMM Do ,YYYY')}} </h3>
    <label>Him</label>
    <input
      type="date"
      name="his_date"
      placeholder="Enter His Date"
      class="form-control"
      v-model="his_date"
    />
    <label>Her</label>
    <input
      type="date"
      name="her_date"
      placeholder="Enter Her Date"
      class="form-control"
      v-model="her_date"
    /><br>
    <input type="submit" value="Check Compatibility!" @click.prevent="submitted" />

    <h5>His Zodiac Sign : {{hisZodiacName}}</h5>
    <h5>Her Zodiac Sign : {{herZodiacName}}</h5>
  </div>
</template>
<script>
export default {
  name: "home",
  data(){
        return {
      		her_date: new Date().toISOString().split('T')[0],
      		his_date : new Date().toISOString().split('T')[0]
    	}
    },
    methods: {
	    submitted() {
	      if (!this.her_date|| !this.his_date) {
	        this.$swal("Empty Input !");
	        return;
	      }

	      //Fire Signs
	      let FireSigns = ['Aries','Leo','Sagittarius'];
	      if(FireSigns.includes(this.hisZodiacName) && FireSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Fire Signs!",
	        	"You guys are  very compatible !",
	        	"success"
		      );
		      return;
	      }

	      //Earth Signs 
	      let EarthSigns = ['Taurus','Virgo','Capricorn'];
	      if(EarthSigns.includes(this.hisZodiacName) && EarthSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Earth Signs!",
	        	"You guys are  very compatible !",
	        	"success"
		      );
		      return;
	      }

	      //Air Signs 
	      let AirSigns = ['Gemini','Libra','Aquarius'];
	      if(AirSigns.includes(this.hisZodiacName) && AirSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Air Signs!",
	        	"You guys are  very compatible !",
	        	"success"
		      );
		      return;
	      }

	      //Water Signs 
	      let WaterSigns = ['Cancer','Scorpio','Pisces'];
	      if(WaterSigns.includes(this.hisZodiacName) && WaterSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Water Signs!",
	        	"You guys are  very compatible !",
	        	"success"
		      );
		      return;
	      }

	      //Fire & Air Signs
	      let FireandAirSigns = ['Aries','Leo','Sagittarius','Gemini','Libra','Aquarius'];
	      if(FireandAirSigns.includes(this.hisZodiacName) && FireandAirSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Fire + Air Signs!",
	        	"You guys are very very compatible !",
	        	"success"
		      );
		      return;
	      }

	      //Earth & Water Signs 
	      let EarthandWaterSigns = ['Taurus', 'Virgo', 'Capricorn','Cancer', 'Scorpio', 'Pisces'];
	      if(EarthandWaterSigns.includes(this.hisZodiacName) && EarthandWaterSigns.includes(this.herZodiacName)){
	      	this.$swal(
		        "Good Match Earth + Water Signs!",
	        	"You guys are very very compatible !",
	        	"success"
		      );
		      return;
	      }

	      this.$swal(
	        "Not A Good Match!",
		    "You guys are not compatible !",
		    "error"
	      );
	    },
    },
    computed: {
	    hisZodiacName: function () {
	    	let myDate = new Date(this.his_date);

			if (myDate.getMonth() == new Date('2011-1-20').getMonth() && myDate.getDate() >= 20 || myDate.getMonth() == new Date('2011-2-20').getMonth() && myDate.getDate() <= 18 ) {
				return "Aquarius";
			}

			if (myDate.getMonth() == new Date('2011-2-20').getMonth() && myDate.getDate() >= 19 || myDate.getMonth() == new Date('2011-3-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Pisces";
			}

			if (myDate.getMonth() == new Date('2011-3-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-4-20').getMonth() && myDate.getDate() <= 19 ) {
				return "Aries";
			}

			if (myDate.getMonth() == new Date('2011-4-20').getMonth() && myDate.getDate() >= 20 || myDate.getMonth() == new Date('2011-5-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Taurus";
			}

			if (myDate.getMonth() == new Date('2011-5-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-6-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Gemini";
			}

			if (myDate.getMonth() == new Date('2011-6-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-7-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Cancer";
			}

			if (myDate.getMonth() == new Date('2011-7-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-8-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Leo";
			}

			if (myDate.getMonth() == new Date('2011-8-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-9-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Virgo";
			}

			if (myDate.getMonth() == new Date('2011-9-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-10-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Libra";
			}

			if (myDate.getMonth() == new Date('2011-10-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-11-20').getMonth() && myDate.getDate() <= 21 ) {
				return "Scorpio";
			}

			if (myDate.getMonth() == new Date('2011-11-20').getMonth() && myDate.getDate() >= 22 || myDate.getMonth() == new Date('2011-12-20').getMonth() && myDate.getDate() <= 21 ) {
				return "Sagittarius";
			}

			if (myDate.getMonth() == new Date('2011-12-20').getMonth() && myDate.getDate() >= 22 || myDate.getMonth() == new Date('2011-1-20').getMonth() && myDate.getDate() <= 19 ) {
				return "Capricorn";
			}

			return "Invalid Input";
			     
	    },
	    herZodiacName: function () {
	    	let myDate = new Date(this.her_date);

			if (myDate.getMonth() == new Date('2011-1-20').getMonth() && myDate.getDate() >= 20 || myDate.getMonth() == new Date('2011-2-20').getMonth() && myDate.getDate() <= 18 ) {
				return "Aquarius";
			}

			if (myDate.getMonth() == new Date('2011-2-20').getMonth() && myDate.getDate() >= 19 || myDate.getMonth() == new Date('2011-3-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Pisces";
			}

			if (myDate.getMonth() == new Date('2011-3-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-4-20').getMonth() && myDate.getDate() <= 19 ) {
				return "Aries";
			}

			if (myDate.getMonth() == new Date('2011-4-20').getMonth() && myDate.getDate() >= 20 || myDate.getMonth() == new Date('2011-5-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Taurus";
			}

			if (myDate.getMonth() == new Date('2011-5-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-6-20').getMonth() && myDate.getDate() <= 20 ) {
				return "Gemini";
			}

			if (myDate.getMonth() == new Date('2011-6-20').getMonth() && myDate.getDate() >= 21 || myDate.getMonth() == new Date('2011-7-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Cancer";
			}

			if (myDate.getMonth() == new Date('2011-7-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-8-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Leo";
			}

			if (myDate.getMonth() == new Date('2011-8-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-9-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Virgo";
			}

			if (myDate.getMonth() == new Date('2011-9-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-10-20').getMonth() && myDate.getDate() <= 22 ) {
				return "Libra";
			}

			if (myDate.getMonth() == new Date('2011-10-20').getMonth() && myDate.getDate() >= 23 || myDate.getMonth() == new Date('2011-11-20').getMonth() && myDate.getDate() <= 21 ) {
				return "Scorpio";
			}

			if (myDate.getMonth() == new Date('2011-11-20').getMonth() && myDate.getDate() >= 22 || myDate.getMonth() == new Date('2011-12-20').getMonth() && myDate.getDate() <= 21 ) {
				return "Sagittarius";
			}

			if (myDate.getMonth() == new Date('2011-12-20').getMonth() && myDate.getDate() >= 22 || myDate.getMonth() == new Date('2011-1-20').getMonth() && myDate.getDate() <= 19 ) {
				return "Capricorn";
			}

			return "Invalid Input";
			      
	    }
   }
};
</script>
<style>
body{
	background: #0d1d24
}
input[type = "date"]{
	background:#33FFBE;
	color:black;
    border: 1px solid green;
    width: 200px;
    height:30px;
    margin:5px;
    border-radius: 3px;
    text-align:center;
}

input[type = "submit"]{
	background: #152238;
	color:white;
	width: 200px;
    height:30px;
    margin:5px;
    border-radius: 5px;
    text-align:center;
}

</style>
