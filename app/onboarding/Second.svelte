<script>
	import First from "./First.svelte"
	import Third from "./Third.svelte"
	import Home from "../Main/Home/Home.svelte"

	import { navigate } from "svelte-native"

	const navigateToNextPage = () =>{
		navigate({
			page: Third,
			transition: {
				name: "slide",
				duration: 500
			}
		})
	}
	const navigateToPrevPage = () =>{
		navigate({
			page: First,
			transition: {
				name: "slideRight",
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
<page>
	<actionBar flat="true" backgroundColor="white">
		  <navigationButton color="orange" text="Go back" android.systemIcon="ic_menu_back" on:tap={navigateToPrevPage} />
		<flexboxLayout width="100%" horizontalAlignment="right">
			<label class="skip" text="Skip" on:tap={goToHome} fontSize="16" verticalAlignment="center" />
		</flexboxLayout>
	</actionBar>
	<gridLayout rows="*, auto" columns="*" padding="15 0" width="100%">
		<stackLayout row="0" verticalAlignment="center" horizontalAlignment="center" padding="0 10">
			<image src="~/images/pic_1.png" height="320" width="320" marginBottom="10"/>
			<label text="Compare Views" horizontalAlignement="center" class="h1" />
			<label text="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s" textWrap="true" horizontalAlignement="center"/>
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