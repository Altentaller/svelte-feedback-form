<script>
	import { imask } from 'svelte-imask';
	
	export let controlType=null;
	export let id;
	export let placeholder="";
	export let rows=null; 
	export let name=null;
	export let type="";
	export let required=null;

	const options = {
		mask: '+{86} 00 0000 0000'
 	};

</script>

<style>
		input,
		textarea {
			display: block;
			width: 100%;
			border: none;
			border: 2px solid #ccc;
			border-radius: 3px 3px 0 0;
			background: white;
			padding: 10px;
			transition: border-color 0.1s ease-out;
			font-weight: 300;
			font-size: 16px;
			resize: none;
		}
	
		input:focus,
		textarea:focus {
			border-color: #ebab2e;
			outline: none;
		}

		.form-control {
			width: 100%;
			margin: 5px 0 15px 0;
		}

	</style>




<div class="form-control">
	{#if controlType === 'textarea'}
		<textarea {rows} {id} {name} placeholder="{placeholder}" />
	{:else if required === 'true'}
		<input type="{type}" {id} {name} placeholder="{placeholder}" required maxlength='40'/>
	{:else if name === 'phone'}
		<input type="{type}" {id} {name} placeholder="{placeholder}" use:imask={options} />
	{:else}
		<input type="{type}" {id} {name} placeholder="{placeholder}" maxlength='40' />
	{/if} 
</div>