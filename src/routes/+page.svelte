<main class="responsive max">
	<h1>GSMST Room Finder</h1>
	<p>Another hastily made webapp by Kat</p>
	<div>
		<div class="">
			<div class="field label border">
				<input type="text" />
				<label>Room Number</label>
				<span class="helper">ex. 1.234</span>
			</div>
        </div>
        <h4 class="center-align">OR</h4>
			<div class="">
				<div class="field suffix border label">
					<select class="active">
						<option value="2.151">McCook</option>
						<option value="2.152">Sorich</option>
						<option value="2.162">Sharpe</option>
						<option value="2.163">Morgan</option>
						<option value="2.164">Spitler</option>
						<option value="2.173">Cossen</option>
						<option value="2.178">Covin</option>
						<option value="2.178">Kohanek</option>
						<option value="2.181">Milsted</option>
						<option value="3.103">Hewa Bosthanthirige</option>
						<option value="3.107">Molnar</option>
						<option value="3.108">Patterson</option>
						<option value="3.121">Hulme</option>
						<option value="3.124">Kastner</option>
						<option value="3.127">Dart</option>
						<option value="3.129">Weeks</option>
						<option value="3.131">Gorgans</option>
						<option value="3.132">Cavenaugh</option>
						<option value="5.146">Boyette</option>
						<option value="5.123">Richardson</option>
						<option value="5.116">Duke</option>
						<option value="5.128">Haynor</option>
						<option value="5.011">Schepens</option>
						<option value="5.024">Coddington</option>
						<option value="5.034">McDonald</option>
						<option value="5.042">Jiang</option>
						<option value="5.044">Amaya</option>
						<option value="5.048">Orozco</option>
						<option value="5.053">Delean</option>
						<option value="5.054">Gomez-Miller</option>
						<option value="5.055">Houng</option>
						<option value="5.056">Burse</option>
						<option value="5.063">Dos Santos</option>
						<option value="5.064">Moore</option>
						<option value="5.201">Rackley</option>
						<option value="5.212">Stamm</option>
						<option value="5.219">Nguyen</option>
						<option value="5.224">Calhoun</option>
						<option value="5.241">Lee</option>
						<option value="5.248">Caldwell</option>
						<option value="5.249">Jayasinghe</option>
						<option value="5.254">Kuninsky</option>
						<option value="5.256">Cox</option>
						<option value="5.257">Son</option>
						<option value="5.258">Bergh</option>
						<option value="5.259">Shaw</option>
						<option value="5.262">Bartholomai</option>
						<option value="5.279">Dore</option>
						<option value="5.302">Burmester</option>
						<option value="5.303">Savio-Ramos</option>
						<option value="5.326">Thurston</option>
						<option value="5.327">Merchant</option>
						<option value="5.336">Tucker</option>
						<option value="5.337">Cook</option>
						<option value="5.338">Stiffler</option>
						<option value="5.339">Rachkovskiy</option>
						<option value="5.341">Bara</option>
						<option value="5.342">Thompson</option>
						<option value="5.343">White</option>
						<option value="5.344">Rawlins</option>
						<option value="5.347">Manspeaker</option>
						<option value="5.348">M. Phillips</option>
						<option value="5.349">Berry</option>
						<option value="5.366">Fowler</option>
						<option value="5.367">Newcomb-Thompson</option>
						<option value="2.102">Ciofi</option>
						<option value="2.103">Johnson</option>
						<option value="2.104">Ott</option>
						<option value="2.107">Andrews</option>
						<option value="2.108">Mayhan</option>
						<option value="2.109">Rubio</option>
						<option value="2.112">Leazenbee</option>
						<option value="2.113">Woodward</option>
						<option value="2.121">Rhine</option>
						<option value="2.136">L. Phillips</option>
						<option value="2.141">Vatalaro</option>
					</select>
					<i>arrow_drop_down</i>
                    <label class="active">Select Teacher</label>
				</div>
			</div>
		</div>
        <button class="round margin" id="submit">Submit</button>
</main>

<script>
    //onMount
    import { onMount } from 'svelte';
    onMount(() => {
    const submit = document.getElementById("submit");
    submit.addEventListener("click", () => {
        const room = document.querySelector("input").value;
        const teacher = document.querySelector("select").value;
        if (room) {
            // If it starts with 2.xxx, it's west wing(redirect to /west)
            if (room.startsWith("2.")) {
                window.location.href = `/west/`;
            // If it start with 3.xxx, it's wild west(redirect to /wild)
            } else if (room.startsWith("3.")) {
                window.location.href = `/wild/`;
            // If it starts with 5.0xx, it's tower ground floor(redirect to /tower/ground)
            } else if (room.startsWith("5.0")) {
                window.location.href = `/tower/ground`;
            // If it starts with 5.1xx, it's tower first floor(redirect to /tower/first)
            } else if (room.startsWith("5.1")) {
                window.location.href = `/tower/first`;
            // If it starts with 5.2xx, it's tower second floor(redirect to /tower/second)
            } else if (room.startsWith("5.2")) {
                window.location.href = `/tower/second`;
            // If it starts with 5.3xx, it's tower third floor(redirect to /tower/third)
            } else if (room.startsWith("5.3")) {
                window.location.href = `/tower/third`;
            } else {
                alert('Sorry, we can\'t find that room. Please try again.')
            }
        } else if (teacher) {
            // Get the value of the teacher select
            const teacher = document.querySelector("select").value;
            // If it starts with 2.xxx, it's west wing(redirect to /west)
            if (teacher.startsWith("2.")) {
                window.location.href = `/west/`;
            // If it start with 3.xxx, it's wild west(redirect to /wild)
            } else if (teacher.startsWith("3.")) {
                window.location.href = `/wild/`;
            // If it starts with 5.0xx, it's tower ground floor(redirect to /tower/ground)
            } else if (teacher.startsWith("5.0")) {
                window.location.href = `/tower/ground`;
            // If it starts with 5.1xx, it's tower first floor(redirect to /tower/first)
            } else if (teacher.startsWith("5.1")) {
                window.location.href = `/tower/first`;
            // If it starts with 5.2xx, it's tower second floor(redirect to /tower/second)
            } else if (teacher.startsWith("5.2")) {
                window.location.href = `/tower/second`;
            // If it starts with 5.3xx, it's tower third floor(redirect to /tower/third)
            } else if (teacher.startsWith("5.3")) {
                window.location.href = `/tower/third`;
            } else {
                alert('Sorry, we can\'t find that teacher. Please try again.')
            }
        }
    });
});
</script>