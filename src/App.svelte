
<script>
  import Name from './Name.svelte'
  import Title from './Title.svelte'
  import Link from './Link.svelte'
  import SVG from './SVG.svelte'
  import Stack from './Stack.svelte'
  import Bunny from './Bunny.svelte'
  import Likes from './Likes.svelte'
  let width
  let height
</script>
<svelte:window bind:innerHeight={height} bind:innerWidth={width} />
<main class='frame'>
  <SVG {width} {height} />
  <div id='info'>
    <Name />
    <Title />
    <Stack />
    <Bunny />
    <Likes />
    
    <Link {width} {height} />
    
  </div>
</main>
<style>
  
  
  
</style>
