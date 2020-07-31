<script>
	import Chance from 'chance'
	let chance = new Chance()
	let company = chance.company()
	let firstName = chance.first()
	let lastName = chance.last()
	let email = chance.string({ length: 10, alpha: true, numeric: true }) + '@yopmail.com'
	let guid = chance.guid()
	let hash = chance.hash()
</script>

<h3>Company</h3>
<span>{company}</span>
<h3>Name</h3>
<span>{firstName} {lastName}</span>
<h3>Email</h3>
<span>{email}</span>
<h3>GUID</h3>
<span>{guid}</span>
<h3>Hash</h3>
<span>{hash}</span>