<script>
	import Chance from 'chance';
	let chance = new Chance();
	let company = chance.company();
	let name = chance.name();
	let email = chance.string({ length: 10, alpha: true, numeric: true }) + '@yopmail.com';
</script>

<h3>Company</h3>
<span>{company}</span>
<h3>Name</h3>
<span>{name}</span>
<h3>Email</h3>
<span>{email}</span>