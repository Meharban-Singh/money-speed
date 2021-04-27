<script>
import TimeCard from "./TimeCard.svelte";

	const people = [
		{
			name: "Jeff Bezos",
			age: 57,
			sources: "Amazon",
			yearToDate: 8_400_000_000,
		},
		{
			name: "Elon Musk",
			age: 49,
			sources: "Tesla, SpaceX, Boring Company",
			yearToDate: 19_000_000_000,
		},
		{
			name: "Mark Zuckerberg",
			age: 36,
			sources: "Facebook",
			yearToDate: 9_600_000_000,
		},
		{
			name: "Warren Buffet",
			age: 90,
			sources: "Berkshire Hathaway",
			yearToDate: 14_900_000_000,
		},
	]	
</script>

<h1>Money-Speed</h1>
<main>
	<div class="container">
		{#each people as p}
			<TimeCard name={p.name} age={p.age} sources={p.sources} yearToDate={p.yearToDate}/>
		{/each}
	</div>
</main>

<style>
	h1{
		background: #8A2387;  /* fallback for old browsers */
		background: -webkit-linear-gradient(to right, #F27121, #E94057, #8A2387);  /* Chrome 10-25, Safari 5.1-6 */
		background: linear-gradient(to right, #F27121, #E94057, #8A2387); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
		padding: 20px;
		margin-bottom: 50px;
		text-align: center;
	}

	main {
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.container {
		display: grid;
		grid-template-columns: auto auto;
		gap: 20px;
	}

	@media screen and (max-width: 1250px){
		.container {
			grid-template-columns: auto;
		}
	}
</style>