<script>
	export let my_name;
	export let name;
	export let sum = 0;
	export let a;
	export let b;
	export let c;

	export let t = 0;
	export function addPoint(){
		sum = sum + 1;
		return sum;
	}

	export function removePoint(){
		sum = sum - 1;
		return sum;
	}

	export function findVertexX(a, b){
		a = Number(a);
		b = Number(b);
		return (-1)*((b)/(2*a));
	}

	export function findVertexY(a, b, c){
		a = Number(a);
		b = Number(b);
		c = Number(c);
		t = (b**2)/(4*a);
		return c-t;
	}

	export function findXIntercept(){


	}

	export function findYIntercept(){


	}

	export function findSolutions(a, b, c){
		a = Number(a);
		b = Number(b);
		c = Number(c);
		return ((-1*b)+Math.sqrt(b**2+((-4)*(a*c))))/(2*a);
	}
</script>

<main>
	<h1>Hello {my_name}!</h1>
	<h3>Hello to the {name}</h3>
	<div class="button__container">
		<p>Counter</p>
		<button class="btn" on:click={addPoint}>+ 1</button>
		<button class="btn-dark" on:click={removePoint}>- 1</button>
		<h5>{sum}</h5>
	</div>
	<br/>
	<div class="name-change">
		<p>Wanna Change The Name?</p>
    <input type="text" bind:value={name}/>
	</div>
	
	<br/>
	
	<div style="
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-contents: center;
	">
		<p>Quadratic Function </p>
		<h5> &#402;(x) = {a||"a"}x&#178; + {b||"b"}&#120; + {c||"c"}</h5>
		a <input type="text" bind:value={a} placeholder="a">
		b <input type="text" bind:value={b} placeholder="b">
		c <input type="text" bind:value={c} placeholder="c">
	</div>
	<div style="
		display:flex;
		flex-direction: column;
	">
		<p>X Vertex : {findVertexX(a, b)}</p>
		<p>Y Vertex : {findVertexY(a, b, c)}</p>
		<p>Real Number Solution : {findSolutions(a,b,c)}</p>
	</div>
	
	
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #3498db;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
	input{
		width: 300px;
		height: 30px;
	}
	.btn{
		color: #3498db;
		border: 1px solid #3498db;
		background-color: white;
	}
	.btn-dark{
		background-color: #2c3e50;
		color: white;
	}
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>