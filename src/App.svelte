<script>
  import { FirebaseApp, User } from "sveltefire";
  import firebase from "firebase/app";
  import "firebase/firestore";
  import "firebase/auth";
  import AuthForm from "./components/AuthForm.svelte";
  import Chats from "./components/Chats.svelte";
  const firebaseConfig = {
    apiKey: "AIzaSyBEEBzUQlTN7DyvlBt6Y6XU4IU4L503oy0",
    authDomain: "svelte-chat-487fe.firebaseapp.com",
    databaseURL: "https://svelte-chat-487fe.firebaseio.com",
    projectId: "svelte-chat-487fe",
    storageBucket: "svelte-chat-487fe.appspot.com",
    messagingSenderId: "553941000601",
    appId: "1:553941000601:web:138c5cdae4eb02731df308",
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
</script>

<style>
  .app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    max-height: 100vh;
  }
</style>

<main class="container section app">
  <FirebaseApp {firebase}>
    <User let:user let:auth>
      <Chats {user} />

      <button class="button is-fullwidth" on:click={() => auth.signOut()}>Leave
        Chat</button>

      <div slot="signed-out">
        <AuthForm {auth} />
      </div>
    </User>
  </FirebaseApp>
</main>
