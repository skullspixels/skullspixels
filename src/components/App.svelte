<script>
  import { onMount } from "svelte";
  //select themes light or dark
  import DarkMode from "svelte-dark-mode";
  let theme;
  var storedTheme = localStorage.getItem('theme') || (window.matchMedia("(prefers-color-scheme: dark)").matches ? "dark" : "light");  
  if (storedTheme){
    theme = storedTheme;
  }else{
    theme = "dark";  
  }

  $: switchTheme = theme === "dark" ? "light" : "dark";
  $: document.body.className = theme;  
  //function resize main
 function getResize(MainDiv) {
  const element = document.querySelector(MainDiv);
  //element.style.border ="1px red solid";
 }

  onMount(async () => {
    //resize screen
    //getResize(".main");

  });

</script>

<style>
     @font-face {
       font-family: "SkullphabetOne";
       src: url("./component/fonts/SkullphabetOne.woff") format("woff"),
         /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
           url("./component/fonts/SkullphabetOne.ttf") format("truetype"); /* Chrome 4+, Firefox 3.5, Opera 10+, Safari 3—5 */
     }  
     :global(.light) {
      background:rgb(185, 185, 185);
      --background-color: rgb(135, 253, 0);
     --text-color: #121416d8;
     --link-color: #543fd7;
     }
    :global(.dark) {
      --background-color: rgb(21, 39, 0);  
      background: #032f62;
      color: #f1f8ff;
    } 
    
    *{
       margin:0px 0px !important;
       padding:0px 0px !important;
       list-style: none;
     }

     body {
       font-size: 1rem;
     }

     main {
       display: grid;
       place-items: top;
       text-align: center;
     }
     .head{

     }
     button{
      background-color: transparent !important;
      border:0px;
      cursor: url("./public/images/cursor-hand-icon-145px.png"), pointer !important;      
    }
    .social{
      background-color: var(--background-color);
     }
    .social div{
       display: inline-block;
     }
     .social img{
       display: inline-block;
     }
     #discord img{
       border:0px transparent;
       width:45px;
       height:45px;
     }
     #switch,  #switch img{
       border:0px transparent;      
       width:45px;
       height:45px;
     }
     #switch{
       float:right !important;
     }
     .link{
       cursor: url("./public/images/cursor-hand-icon-145px.png"), pointer !important;
     }
              
     .logo{
       font-family: "SkullphabetOne";
       font-size: 128px;
       background: -webkit-linear-gradient(#ff9100, rgb(63, 18, 0));
       margin-top:15px !important;
       -webkit-background-clip: text;
       -webkit-text-fill-color: transparent;
     }
     .collection{
       width:100%;
       text-align:center;
     }
     .rounded{
        border:0px black solid;
        border-radius: 20px !important;
        display: inline-block;
        margin:0px 0px !important;
        overflow: hidden !important;
        padding:0px 0px !important;  
        width:25% !important;
     }
     .collection img{
        margin:0px 0px !important;
        overflow: hidden !important; 
        width:100% !important;      
     }
   </style>
   <main>
    <div class="main">
      <div class="head">
        <ul>
          <li class="social">
            <div class="link" id="twitter">
              <a href="https://twitter.com/skullspixels" target="_blank" >
                <img src="./public/images/twitter-icon-{switchTheme}-45px.png" alt="https://discord.gg/T2SsMp78" />
              </a>
              <a href="https://discord.gg/T2SsMp78" target="_blank" >
                <img src="./public/images/discord-icon-{switchTheme}-45px.png" alt="https://discord.gg/T2SsMp78" />
              </a>              
            </div>
            <div class="link" id="switch">
              <button on:click={() => (theme = switchTheme)}>
                <img src='./public/images/icon-{switchTheme}-theme.png' alt='Dark Theme'/> 
              </button>
            </div>
          </li>
          <li class="logopanel"><div class="logo">Skulls & Pixels</div></li>
          <li class="description">Art creator in Tezos e ETH block chain</li>
        </ul>
      </div>
      <div class="collection">
        <div class="rounded">
          <img src="https://ipfs.io/ipfs/QmaBUyjryWHyH7YjF9KLLHcqxu2mmit4cS1RZCo6yctgqj" alt="" />
          <div><a href="https://objkt.com/collection/KT1EgbW227kcXaGEbqTJwDzo8joCCAkFuEaP" target="_black">objkt.com</a></div>
        </div>
        <div class="rounded">
          <img src="https://ipfs.io/ipfs/QmXFv15WbF7h8gVVgCwZddqUjKPv5LwPDSzYCB8Kp4cdUd" alt="" />
          <div><a href="https://objkt.com/collection/KT1S21AFKbjXYzsuLtwi7xWzrTBH7qbPkikE" target="_black">objkt.com</a></div>          
        </div>   
        <div class="rounded">
          <img src="https://ipfs.io/ipfs/QmaR8Mr7BSRDwYgWQ65VWb1jj2izowLnxkjAf8gLtSBXwn" alt="" />
          <div><a href="https://objkt.com/collection/KT1SRuzSjPPB2Yow57nxwUgQpFVhXoh52EHb" target="_black">objkt.com</a></div>          
        </div>   
        <div class="rounded">
          <img src="https://ipfs.io/ipfs/QmYZToG4nWurEVQVUKPjSJ5ELNSPGko4fbmnoN4P5VdjAK" alt="" />
          <div><a href="https://objkt.com/collection/KT1Rqq1kU9uQDuPDc3EqW2AzfbJgmBNHZHfa" target="_black">objkt.com</a></div>          
        </div>   
        <div class="rounded">
          <img src="https://ipfs.io/ipfs/QmYaSaE4fP3VEi45dCD3ZLRswArnRhZMUbHraYXzqsKrBU" alt="" />
          <div><a href="https://teia.art/skullspixels" target="_black">teia.art</a></div>          
        </div>                           
      </div>
    </div>
</main>