<script>
  export let auth;
  let mode = "signIn";
</script>

<h1 class="title has-text-info has-text-centered">Svelte Chat</h1>
<h2 class="title">{mode === 'signIn' ? 'Sign In' : 'Sign Up'}</h2>
