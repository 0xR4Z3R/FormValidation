# FormValidation

Simple form Validation 

Link here : 
https://0xr4z3r.github.io/FormValidation/index.html

Username ---> only letter

function allLetter(inputtxt)
  	{
   		var letters = /^[A-Za-z]+$/;

   		if(inputtxt.match(letters))
     	{
      		return true;
     	}else
        {
     		return false;
     	}
   }

Password ----> atleast one uppercase one lowercase  and one number

function CheckPassword(inputtxt) 
	{ 
		var passw = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{6,20}$/;
		if(inputtxt.match(passw)) 
		{ 
			return true;
		}
		else
		{ 
			return false;
		}
	}

Student ID -----> only 9 digit number

  function CheckSID(inputtxt) 
	{ 

		var passw = /^\d{9}$/;
		if(inputtxt.match(passw)) 
		{ 
			return true;
		}
		else
		{ 
			return false;
		}
	}

Message box -----> you can only type up to 25 words

function count_words(event)
	{
		var WC;
		var MaxWords = 26;


		var str1 = document.getElementById("message").value;

		//exclude  start and end white-space
		str1 = str1.replace(/(^\s*)|(\s*$)/gi,"");
		//convert 2 or more spaces to 1
		str1 = str1.replace(/[ ]{2,}/gi," ");
		// exclude newline with a start spacing
		str1 = str1.replace(/\n /,"\n");

		var tokens = str1.split(/ +/);
		var limitedText;

		WC = tokens.length;

		MaxWords = MaxWords - WC;

		if(MaxWords<0){

			//console.log(MaxWords);
			event.preventDefault();
			return false;
		}

	 document.getElementById("wc").innerHTML = MaxWords;


    }
    
    
    buttonPress ----> it checked for all the field in this function 
    
    function buttonPressed()
	{

	var msg1 = document.getElementById("m1");
	var msg2 = document.getElementById("m2");
	var msg3 = document.getElementById("m3");
	var msg4 = document.getElementById("m4");
	var msg5 = document.getElementById("m5");
	var msg6 = document.getElementById("m6");


		 var usernameString = document.getElementById("username").value;
		 var passwordString = document.getElementById("password").value;
		 var SIDString = document.getElementById("SID").value;
		 var MessageString = document.getElementById("message").value;


		 msg6.innerHTML = " " ;


		 document.getElementById("form").style.border = "3px solid white";
		 document.getElementById("username").style.border = "3px solid white";
		 document.getElementById("password").style.border = "3px solid white";
		 document.getElementById("SID").style.border = "3px solid white";
		 document.getElementById("message").style.border = "3px solid white";
		 document.getElementById("submitBtn").style.border = "3px solid white";

		 if( usernameString.length == 0 || passwordString.length == 0 
		 	|| SIDString.length == 0 || MessageString.length == 0){

			msg5.innerHTML = "You need to fill out all fields";
			document.getElementById("form").style.border = "3px solid red";
		 	document.getElementById("username").style.border = "3px solid red";
		 	document.getElementById("password").style.border = "3px solid red";
		 	document.getElementById("SID").style.border = "3px solid red";
		 	document.getElementById("message").style.border = "3px solid red";
		 	document.getElementById("submitBtn").style.border = "3px solid red";

		 } else{


		 	if(allLetter(usernameString)==false){
		 	
		 		msg1.innerHTML = "Username needs to be all letters";
		 		document.getElementById("username").style.border = "3px solid red";

		 	} else{
		 		
		 		msg1.innerHTML = " ";
		 		document.getElementById("username").style.border = "3px solid white";
		 	}

		 	if(CheckPassword(passwordString)==false){
		 	
		 		msg2.innerHTML = "one UC,one LC letter and one digit"
		 		document.getElementById("password").style.border = "3px solid red";

		 	} else{
		 	
		 		msg2.innerHTML = " "
		 		document.getElementById("password").style.border = "3px solid white";
		 	}

		    if(CheckSID(SIDString)==false){
		 	
		 		msg3.innerHTML = " 9 digits number"
		 		document.getElementById("SID").style.border = "3px solid red";

		 	} else{
		 		
		 		msg3.innerHTML = " "
		 		document.getElementById("SID").style.border = "3px solid white";
		 	}

		 }

		 if(allLetter(usernameString)==true && CheckPassword(passwordString)==true && CheckSID(SIDString)==true){

		 	document.getElementById("form").style.border = "3px solid green";
		 	document.getElementById("username").style.border = "3px solid green";
		 	document.getElementById("password").style.border = "3px solid green";
		 	document.getElementById("SID").style.border = "3px solid green";
		 	document.getElementById("message").style.border = "3px solid green";
		 	document.getElementById("submitBtn").style.border = "3px solid green";

		 	document.body.style.background = "url('https://images.unsplash.com/photo-1487029752779-a0c17b1f5ec9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1050&q=80')";

		   msg6.innerHTML = "Form submitted Succesfully ";
		   msg5.innerHTML = "";

		 }
     
     
     ...:)
     
     
     ----> Reset Function
     
     function ResetPressed(){

		var msg6 = document.getElementById("m6");

		document.getElementById("form").style.border = "3px solid white";
		document.getElementById("username").style.border = "3px solid white";
		document.getElementById("password").style.border = "3px solid white";
		document.getElementById("SID").style.border = "3px solid white";
		document.getElementById("message").style.border = "3px solid white";
		document.getElementById("submitBtn").style.border = "3px solid white";

		document.getElementById("message").innerHTML = " ";
		msg6.innerHTML = " ";
	}
     
    
    
    
