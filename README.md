Test
<!DOCTYPE html>
<html>
<body>
	<h1>
		Project #2
	</h1>
		<font face ='Courier New'>
	<script>
	var days = 7;
	var Sday = 1;
	var month = 1;
	var choice = 0;
	var ans1 = " ";
	var ans2 = " ";
	var ans3 = " ";
	var Mname = ["Enero", "Febrero","Marzo", "Abril", "April","Mayo", "Junio",
				 "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre",
				 "January", "Febuary", "March", "April", "May", "June", "July", "August",
				 "September", "October", "Novermber", "December"];
	var Dname = ["Domingo", "Lunes", "Martes", "Miercoles", "Jueves", "Viernes", "Sabado", 
				 "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];	
	var max = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
	var length = 0;
	var Dstart = 0;
	var Blength = 0;
	
	//Spanish or English
	ans3 = prompt('Do you want Spanish or English? 0=Spanish 1= English');
	choice = parseInt(ans3)
	
	//ask for the day
	ans1 = prompt('What Day Will we start on? (0-6) Sunday = 0  Saterday = 6');
	Dstart = parseInt(ans1);
	num = Dstart * -1 + 1;
	
	//ask for the month
	ans2 = prompt('What month do you want to see? (1-12)');
	month = parseInt(ans2);
	

	//sets up Month and day names in language of choice
	
	if(choice == 0){
		document.write(Mname[month - 1] + "<br>" + "<br>");
		document.write('|');
		for(var j = 0; j < 7; j++){
			document.write(Dname[j]);
			for(var k = 0; k+Dname[j].length <= 9; k++){
				document.write("&nbsp");
			}
			document.write('|');
		}
		document.write("<br>");
	} else {
		document.write(Mname[month + 12] + "<br>" + "<br>");
		document.write('|');
		for(var j = 0; j < 7; j++){
			document.write(Dname[j + 7]);
			for(var k = 0; k+Dname[j + 7].length <= 9; k++){
				document.write("&nbsp");
			}
			document.write('|');
		}
		document.write("<br>");
	}	
	
	//sets up calender chart
		//sets up top bar
	for(var e = 0; e < 5; e++){
		for(var x = 0; x < days; x ++){
			document.write('|');
			for(var a = 0; a < 10; a ++){
				document.write('-');
			}
		}	
		document.write('|');
		document.write("<br>");
		
		//sets up inner cubes with numbers inside
		for(var f = 0; f < days; f ++){
			document.write('|');
			if(num <= 0){
				document.write("&nbsp" + "&nbsp");
			}else if(num > max[month - 1]){
				document.write("&nbsp" + "&nbsp");
			}else if(num < 10){
				document.write('0' + num);
			}else{
				document.write(num);
			}
			Blength = 2;
			if(num == 1 && month == 1){
				document.write(" Holiday");
				Blength += 8;
			}else if(num == 4 && month == 7){
				document.write(" Holiday");
				Blength += 8;
			}else if(num == 31 && month == 10){
				document.write(" Holiday");
				Blength += 8;
			}else if(num == 25 && month == 12){
				document.write(" Holiday");
				Blength += 8;
			}
			num+=1;
			for(var g = 0; g + Blength < 10; g++){
				document.write("&nbsp");
			}
		} 
		document.write('|');
		document.write("<br>");
		
		//finishes body of the cubes
		for(var b = 0; b < 3; b ++){
			for(var c = 0; c < days; c ++){
				document.write('|');
				for(var d = 0; d < 10; d ++){
					document.write("&nbsp");
				}
			}
			document.write('|');
			document.write("<br>");
		}
	}
	
	//sets up bottom bar
	for(var x = 0; x < days; x ++){
		document.write('|');
		for(var a = 0; a < 10; a ++){
			document.write('-');
		}
	}
	document.write('|');
	document.write("<br>");
	
		
	</script>
</body>
</html>
Test
