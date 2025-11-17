<script lang="ts">
    import { browser } from "$app/environment";
	import Header from "$lib/ui/Header.svelte";
	import Landing from "$lib/ui/Landing.svelte";
	import SetUp from "$lib/ui/SetUp.svelte";
	import ContributionGuide from "$lib/ui/ContributionGuide.svelte";
	import ToTopButton from "$lib/ui/ToTopButton.svelte";
	import AboutRivETH from "$lib/ui/AboutRivETH.svelte";

    let showScrollToTopButton: boolean = $state(false);

    if (browser) {
        window.onscroll = function() {
            if (window.scrollY > 100) {
                showScrollToTopButton = true;
            } else { 
                showScrollToTopButton = false;
            }
        }
    }
</script>

<div>
    <Header/>
    <Landing/>
    <AboutRivETH/>
    <SetUp/>
    <ContributionGuide/>

    {#if showScrollToTopButton} 
        <ToTopButton/>
    {/if}
</div>

<!-- nav -->