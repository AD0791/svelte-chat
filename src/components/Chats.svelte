<script>
  import AppendMessage from "./AppendMessage.svelte";

  import { Collection } from "sveltefire";

  export let user;
</script>

<Collection path={'/chat'} let:ref={chatsRef} let:data={messages}>
  <AppendMessage {chatsRef} {user} />
</Collection>
