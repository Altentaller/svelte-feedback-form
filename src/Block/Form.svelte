<script>
	import Button from '../UI/Button.svelte'; 
    import Input from '../UI/Input.svelte'; 

	function submitForm(){
		function sendData() {
			const XHR = new XMLHttpRequest();
			const FD = new FormData( order );
			XHR.open( "POST", "https://your-domain.com/mailer/smart.php" );
			XHR.send( FD );
		}

		const order = document.getElementById( "order" );
		order.addEventListener( "submit", function ( event ) {
			event.preventDefault();
			sendData();
			alert( 'Sent!' );	
			event.target.reset(); 
		} );
	}

</script>
    
<style>
	#feedback{
		display: flex;
		justify-content: space-around;
		align-items: flex-start;
		width: 100%;
		height: 100%;
		box-sizing: border-box;
		padding: 50px 0 20px 0;
		min-height: 400px;
		background: #f1f1f1;
		font-size: 19px;
	}

	.form{
		width: 480px;
		margin-top: 70px;
		border: 5px solid #465a82;
		background: #fff;  
	}

	h2{
		text-align: center;
		font-size: 30px;
		font-weight: 500;
	}

	form{
		width: 400px;
		margin: 0 auto;   
		padding: 5px 20px 20px 20px;
	}

</style>

<section id="feedback">
    <div class="form">
        <h2>Feedback Form</h2>

		 <form id="order" on:submit|preventDefault={submitForm}>
            <Input 
                id='name' 
				name='name'
                placeholder='Your name' 
                type='text'/>
            <Input 
                id='phone' 
				name='phone'
				placeholder='+86 00 0000 0000'
                type='text'/>
            <Input 
                id='email' 
				name='email'
                placeholder='Email *' 
                type='email'
				required="true"/>
            <Input 
                id='description' 
				name='description'
                placeholder='Message' 
                controlType='textarea'
                rows='2' />
            
            <Button on:click={submitForm} type="submit" caption="📧 Submit" />

        </form> 
    </div>
    
</section>
