<script>
    import "../app.css";
    import Footer from "../components/Footer.svelte";
    import Header from "../components/Header.svelte";
    let y;
    let innerWidth=0;
    let innerHeight=0;
    function goTop(){
        document.body.scrollIntoView();
    }
  </script>
  <div class="relative flex flex-col max-w-[1440px] mx-auto w-full text-sm sm:text-base min-h-screen">
    <div class={`fixed w-full bottom-0 duration-200 flex p-10 z-[10] ${y > 0 
        ? 'opacity-full pointer-events-auto'
        : 'pointer-events-none opacity-0'}`}>
        <button>
            <i class="fa-solid fa-arrow-upx"></i>
        </button>
    </div>
    <Header/>
    <slot />
    <Footer/>
  </div>
  <svelte:window bind:innerWidth bind:innerHeight bind:scrollY={y}></svelte:window>