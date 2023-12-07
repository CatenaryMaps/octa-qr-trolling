<script lang="ts">
	import { onMount } from "svelte";
     import "../app.css";
     import QRCode from 'qrcode'

     function regenerateQrCode(str: string) {
        QRCode.toCanvas(document.getElementById('hack_qr'), str, function (error:any) {
    if (error) console.error(error)
    console.log('success!');
  });

    
     }

     onMount(() => {
        regenerateQrCode("qMmtIAScbNOkH9V8uaoHUA==X3H1mF/u65kXDR7342tqRA==|2024-01-30T10:59:59.000Z|" + new Date().toISOString());

        setInterval(() => {
            regenerateQrCode("qMmtIAScbNOkH9V8uaoHUA==X3H1mF/u65kXDR7342tqRA==|2024-01-30T10:59:59.000Z|" + new Date().toISOString());
        }, 2000)})

    
     </script>
     <link rel="preconnect" href="https://fonts.googleapis.com">
     <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="true">
     <link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible:ital,wght@0,400;0,700;1,400;1,700&display=swap" rel="stylesheet">

     <title>Catenary Maps - OC Fares</title>

<div class='flex flex-col h-screen overflow-y-none'>
    <div class='relative h-64 flex flex-col'>
       <div>
        <div class='absolute top-0 overflow-x-clip h-[50%]  fudie bg-[#3b76bb]'>

            <div class='fudieblocktop'></div>
            <div class='fudieblocktop'></div>

            <div class='fudieblocktop'></div>
        </div>
        
        <div class='absolute bottom-0 overflow-x-clip h-[50%] bg-green-500 bg-[#5c92cd] fudie'>

            <div class='fudieblockbottom'></div>
            <div class='fudieblockbottom'></div>
            <div class='fudieblockbottom'></div>
        </div>
       </div>
        <div class='my-auto text-white text-2xl flex flex-row z-50'><p class='mx-auto font-bold text-4xl'>OC BUS</p></div>
    </div>

    <div class='flex flex-row h-full flex-grow'><canvas id='hack_qr' class='mx-auto w-[250px] h-[250px] my-auto'></canvas></div>
    <div class='bg-[#3876ba] font-bold text-white flex flex-row py-3'><p class='mx-auto text-2xl'>Ticket Expires</p></div>
    <div class='bg-[#1d59a9] font-bold text-white flex flex-row py-3'><p class='mx-auto text-2xl'>01/30/2024 2:59 AM</p></div>
</div>

<style>
    body {
        overflow-y: hidden;
        font-family: 'Atkinson Hyperlegible', sans-serif !important;
    }

    .fudie {
      display: flex;
      width: 300%;
      animation: scrollAnimation 5s linear infinite;
      
      
    }

    .fudieblocktop {
        
      flex: 1;
      height: 100%;
    }

    .fudieblocktop:nth-child(1) {
        
        background-color: #3b76bb;
    }

    .fudieblocktop:nth-child(2) {
     
        background-color: #5c92cd;
    }

    .fudieblocktop:nth-child(3) {
        
        background-color: #3b76bb;
    }

    .fudieblockbottom {
        
        flex: 1;
        height: 100%;
      }
  
      .fudieblockbottom:nth-child(1) {
        background-color: #1d59a9;
      }
  
      .fudieblockbottom:nth-child(2) {
        background-color: #3876ba;
      }

      .fudieblockbottom:nth-child(3) {
        background-color: #1d59a9;
      }

    @keyframes scrollAnimation {
      from {
        transform: translateX(0%);
      }
      
      to {
        transform: translateX(-66.6%);
      }
    }

    
</style>