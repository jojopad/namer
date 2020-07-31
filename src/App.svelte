<script>
	import Chance from 'chance';
	import Copy from './Copy.svelte'
	import { onMount } from 'svelte';

	let chance = new Chance()
	let company, name, firstName, lastName, email, guid, hash;

	function generate() {
		company = chance.company();
		firstName = chance.first();
		lastName = chance.last();
		let emailTmp = firstName + lastName + chance.string({ length: 10, alpha: true, numeric: true }) + '@yopmail.com';
		email = emailTmp.replace(/\s/g, '');
		guid = chance.guid();
		hash = chance.hash();
	}

	function copy(value) {
		navigator.clipboard.writeText(value);
	}

	onMount(async () => generate());
</script>

<div style="margin-left: 50px; margin-top: 50px">
	<button on:click="{generate}">Generate</button>

	<h3>Company</h3>
	<Copy value="{company}"/>
	<span>{company}</span>


	<h3>First Name</h3>
	<Copy value="{firstName}"/>
	<span>{firstName}</span>

	<h3>Last Name</h3>
	<Copy value="{lastName}"/>
	<span>{lastName}</span>

	<h3>Email</h3>
	<Copy value="{email}"/>
	<span>{email}</span>

	<h3>GUID</h3>
	<Copy value="{guid}"/>
	<span>{guid}</span>

	<h3>Hash</h3>
	<Copy value="{hash}"/>
	<span>{hash}</span>
</div>
