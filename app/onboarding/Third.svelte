<script>
	import Second from "./Second.svelte"
	import Home from "../Main/Home/Home.svelte"
	import { navigate } from "svelte-native"

	const navigateToNextPage = () =>{
		navigate({
			page: Home,
			transition: {
				name: "slide",
				duration: 500
			},
			clearHistory: true
		})
	}
	const navigateToPrevPage = () =>{
		navigate({
			page: Second,
			transition: {
				name: "slideRight",
				duration: 500
			}
		})
	}
</script>
<page>
	<actionBar flat="true" backgroundColor="white">
		<navigationButton color="orange" text="Go back" android.systemIcon="ic_menu_back" on:tap={navigateToPrevPage} />
		<flexboxLayout orientation="horizontal" horizontalAlignment="right">
		</flexboxLayout>
	</actionBar>
	<gridLayout rows="*, auto" columns="*" padding="15 0" width="100%">
		<stackLayout row="0" verticalAlignment="center" horizontalAlignment="center" padding="0 10">
			<image src="~/images/pic_3.png" height="320" width="320" marginBottom="10"/>
			<label text="Free Modules" horizontalAlignement="center" class="h1" />
			<label text="Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old." textWrap="true" horizontalAlignement="center"/>
		</stackLayout>
		<stackLayout row="1">
			<button on:tap={navigateToNextPage}>Get Started</button>
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