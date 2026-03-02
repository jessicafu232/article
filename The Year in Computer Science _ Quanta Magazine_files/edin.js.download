jQuery(document).ready(function($) {

	$('form.edin-form').each(function() {

		$( this ).validate({ 
	        rules: {
	            name: {
	                required: false
	            },
	            gender: {
	                required: true
	            },
	            input_country: {
	            	required: true
	            },
	            input_age: {
	            	required: true,
	            	number: true
	            },
	            input_rating: {
	            	required: true
	            },
	            input_grade: {
	            	required: true
	            },
	            input_experience: {
	            	required: true
	            }
	        },
	        errorPlacement: function(error, element) {
				if(element.is(':radio')){
					error.appendTo(element.parent());
				} else {
					error.insertAfter(element);
				}
			},
	        submitHandler: function(form) {
//		    	form.submit();
		    	$.ajax({
					url: EDIN.ajaxurl,
					type: 'POST',
					data: f.serialize(),
					success: function( response ) {
						//@todo handle errors
						if( response.new_id == 0 ){
							result.html( 'Something went wrong with your form submission, please try again!' );
						}else{
							result.html( response.message );
							f.find('.section').hide();							
						}
					}
				});

			}
	    });

		var f = $(this),
			result = f.find('.result');

		//handle submission
/*		f.on('submit', function(evt) {
			evt.preventDefault();

			
		});*/

	});

});