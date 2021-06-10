<script>
   import Header from './components/Header.svelte'
   import Footer from './components/Footer.svelte'
   import CreatePollForm from './components/CreatePollForm.svelte'
   import Tabs from './shared/Tabs.svelte'
   
   let items = ['Current Polls', 'Add New Poll']
   let activeItem = 'Current Polls'
</script>

<Header/>
<main>
   <Tabs on:tabChange={(e)=>activeItem = e.detail} {activeItem} {items}/>
   {#if activeItem === 'Current Polls'}
      <p>Current polls component</p>
   {:else if activeItem === 'Add New Poll'}
      <CreatePollForm/>
   {/if}
</main>
<Footer/>

<style>
	main {
		width: 100%;
		max-width: 960px;
		margin: 40px auto;
	}
</style>
