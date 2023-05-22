<script>
	import { navigate } from "svelte-native"
	import { fly } from 'svelte/transition';

	import Second from "./Second.svelte"
	import Home from "../Main/Home/Home.svelte"

	const navigateToNextPage = () =>{
		navigate({
			page: Second,
			animated: true,
			transition: {
				name: "slide",
				duration: 500
			}
		})
	}
	const goToHome = () => {
		navigate({
			page: Home,
			animated: true,
			transition: {
				name: "slide",
				duration: 500
			}
		})
	}
</script>
<page statusBarStyle="light">
	<actionBar flat="true" backgroundColor="white">
		<stackLayout orientation="horizontal" horizontalAlignment="right">
			<label class="skip" text="Skip" on:tap={goToHome} fontSize="16" verticalAlignment="center" />
		</stackLayout>
	</actionBar>
	<gridLayout rows="*, auto" columns="*" padding="15 0" width="100%">
		<stackLayout row="0" verticalAlignment="center" horizontalAlignment="center" padding="0 10">
			<image src="~/images/pic_2.png" height="320" width="320" marginBottom="10"/>
			<label text="Create Templates" horizontalAlignement="center" class="h1" />
			<label text="It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using." textWrap="true" horizontalAlignement="center"/>
		</stackLayout>
		<stackLayout row="1">
			<button on:tap={navigateToNextPage}>Next</button>
		</stackLayout>
	</gridLayout>
</page>

<style>
	button{
		background-color: orange;
		color: white;
		border-radius: 50%;
		elevation:0;
	}

	label {
		text-align: center;
	}
	.skip{
		text-decoration: underline;
	}
</style>