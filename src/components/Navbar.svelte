<script>
    import Router, {location, link} from 'svelte-spa-router';
    import Home from "../routes/Home.svelte";
    import Convert from "../routes/Convert.svelte";
</script>

<div class="navbar bg-[#1A1A1A] text-white">
    <div class="navbar-start">
        <div class="dropdown">
            <label tabindex="0" class="btn btn-ghost lg:hidden">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" /></svg>
            </label>
            <ul tabindex="0" class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-[#1A1A1A] rounded mt-5 w-52">
                <li><a href="/"><i class="fa-solid fa-house"></i> Anasayfa</a></li>
                <li><a href="/#/convert"><i class="fa-brands fa-bandcamp"></i> Dönüştür</a></li>
            </ul>
        </div>
        <a class="text-xl ml-3">Contch</a>
    </div>
    <div class="navbar-center hidden lg:flex">
        <ul class="menu menu-horizontal p-0">
            <li><a href="/"><i class="fa-solid fa-house"></i> Anasayfa</a></li>
            <li><a href="/#/convert"><i class="fa-brands fa-bandcamp"></i> Dönüştür</a></li>
        </ul>
    </div>
    <div class="navbar-end">
        <a href="https://twitter.com/queaxtra"><i class="fa-brands fa-twitter mr-2 text-xl"></i></a>
        <a href="https://github.com/Queaxtra/contch"><i class="fa-brands fa-github ml-2 mr-2 text-xl"></i></a>
    </div>
</div>

<Router routes={{
    "/": Home,
    "/convert": Convert
}} />