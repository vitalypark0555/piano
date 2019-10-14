# piano
Simple JavaScript Piano

Day #1 of JavaScript learning

You can play piano by clicking on keys

CSS taken from https://codepen.io/zastrow/pen/oDBki

Main script:

                            
            document.addEventListener('click', function (event) { //catching click event

          
				if (!event.target.matches('.key')) //checking if a document element has a 'key' css class
					return;

				event.preventDefault();
         
				keyCode = event.target.getAttribute('data-key');  //getting a key code of a clicked key
         
				const audio = document.querySelector(`audio[data-key="${keyCode}"]`);  //getting audio by a key code
         
				if(!audio)  //checking if audio is found
			       	return;
			         		
				audio.currentTime = 0; //resetting time of audio playing to make it available to play again 
          
				audio.play(); //playing audio
			}, false);
