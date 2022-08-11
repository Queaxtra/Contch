<script>
    import trdoviz from "tr-doviz"
    trdoviz().then(data => {
        // Dolar bilgi
        const dolarfiyat = data.dolar;
        const dolar = dolarfiyat.toFixed(2);
        const dolartarih = data.tarih;
        document.getElementById("fiyat").innerHTML = dolar + "₺";
        document.getElementById("tarih").innerHTML = "<i class=\"fa-solid fa-clock\"></i> " + dolartarih;

        // Euro bilgi
        const eurofiyat = data.euro;
        const euro = eurofiyat.toFixed(2);
        const eurotarih = data.tarih;
        document.getElementById("fiyat2").innerHTML = euro + "₺";
        document.getElementById("tarih2").innerHTML = "<i class=\"fa-solid fa-clock\"></i> " + eurotarih;
    })
</script>

<center>
    <h2 class="mt-20 text-5xl text-white font-extrabold">Contch</h2>
    <p class="mt-5 text-xl text-gray-400">Basit bir döviz hesaplayıcısıdır.</p>

    <h2 class="text-white text-4xl font-semibold mt-20 relative top-10">Canlı <span class="text-orange-600">Döviz</span></h2>
    <div class="stats shadow rounded bg-[#1A1A1A] mt-20">
        <div class="stat">
            <div class="stat-title">Güncel Dolar</div>
            <div class="stat-value" id="fiyat"></div>
            <div class="stat-desc text-lg" id="tarih"></div>
        </div>
    </div>
    <div class="stats shadow rounded bg-[#1A1A1A] mt-20">
        <div class="stat">
            <div class="stat-title">Güncel Euro</div>
            <div class="stat-value" id="fiyat2"></div>
            <div class="stat-desc text-lg" id="tarih2"></div>
        </div>
    </div>
    <p class="text-gray-500 mt-5">*Bu değerler güncel olarak değişmektedir.</p>
</center>