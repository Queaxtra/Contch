<script>
    import trdoviz from "tr-doviz";
    import toast, {Toaster} from 'svelte-french-toast';
    let dolargiris = "";
    let eurogiris = "";

    function dolarHesapla() {
        trdoviz().then(data => {
            const dolarfiyat = data.dolar * dolargiris;
            toast.success(`${dolargiris} doların fiyatı: ${dolarfiyat.toFixed(2)}₺`);
        })
    }
    function euroHesapla() {
        trdoviz().then(data => {
            const eurofiyat = data.euro * eurogiris;
            toast.success(`${eurogiris} euronun fiyatı: ${eurofiyat.toFixed(2)}₺`);
        })
    }
</script>

<center>
    <h2 class="relative mt-32 text-4xl text-white font-semibold">Hesap Makinesi</h2>
    <p class="mt-5 text-xl text-gray-500">Girdiğiniz değerlere göre fiyat hesaplarsınız.</p>
    <div class="stats shadow rounded bg-[#1A1A1A] mt-24">
        <div class="stat">
            <div class="stat-title text-2xl text-white opacity-100">Dolar <span class="text-orange-600">Hesapla</span></div>
            <div class="stat-value text-lg text-black opacity-100">
                <input type="number" bind:value="{dolargiris}" class="relative mt-5 w-64 h-10 rounded p-5 text-center" placeholder="Lütfen bir sayı giriniz.">
            </div>
            <div class="stat-desc text-lg opacity-100">
                <Toaster />
                <button class="btn rounded relative mt-5 bg-orange-600 text-white hover:bg-orange-500" on:click={dolarHesapla} disabled={dolargiris == ""}>Hesapla</button>
            </div>
        </div>
    </div>
    <div class="stats shadow rounded bg-[#1A1A1A] mt-20">
        <div class="stat">
            <div class="stat-title text-2xl text-white opacity-100">Euro <span class="text-orange-600">Hesapla</span></div>
            <div class="stat-value text-lg text-black opacity-100">
                <input type="number" bind:value="{eurogiris}" class="relative mt-5 w-64 h-10 rounded p-5 text-center" placeholder="Lütfen bir sayı giriniz.">
            </div>
            <div class="stat-desc text-lg opacity-100">
                <Toaster />
                <button class="btn rounded relative mt-5 bg-orange-600 text-white hover:bg-orange-500" on:click={euroHesapla} disabled={eurogiris == ""}>Hesapla</button>
            </div>
        </div>
    </div>
</center>