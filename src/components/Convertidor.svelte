<script>
    let tengo = "USD";
    let quiero = "EUR";
    let cantidad = 0;
    let total = 0;
    let monedas = ["USD", "EUR", "LIBRA"];

    function convertir() {
        switch (tengo) {
            case "USD":
                if (quiero == "USD") {
                    total = cantidad;
                }
                if (quiero == "EUR") {
                    total = cantidad * 0.84;
                }
                if (quiero == "LIBRA") {
                    total = cantidad * 0.76;
                }
                break;
            case "EUR":
                if (quiero == "USD") {
                    total = cantidad * 1.18;
                }
                if (quiero == "EUR") {
                    total = cantidad;
                }
                if (quiero == "LIBRA") {
                    total = cantidad * 0.9;
                }
                break;
            case "LIBRA":
                if (quiero == "USD") {
                    total = cantidad * 1.32;
                }
                if (quiero == "EUR") {
                    total = cantidad * 1.11;
                }
                if (quiero == "LIBRA") {
                    total = cantidad;
                }
                break;
        }
    }
</script>

<style>
</style>

<div>
    <div class="container mt-2">
        <div class="row">
            <div class="col-lg-12">
                <div class="form-group">
                    <label for="cantidad">Ingrese cantidad</label>
                    <input
                        type="numer"
                        class="form-control form-control-lg"
                        id="cantidad"
                        bind:value={cantidad}
                        on:input={() => convertir()} />
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <div class="form-group">
                    <label for="tengo">Tengo</label>
                    <!-- svelte-ignore a11y-no-onchange -->
                    <select
                        class="form-control form-control-lg"
                        id="tengo"
                        bind:value={tengo}
                        on:change={() => convertir()}>
                        {#each monedas as moneda}
                            <option>{moneda}</option>
                        {/each}
                    </select>
                </div>
            </div>
            <div class="col-lg-6">
                <div class="form-group">
                    <label for="quiero">Quiero</label>
                    <!-- svelte-ignore a11y-no-onchange -->
                    <select
                        class="form-control form-control-lg"
                        id="quiero"
                        bind:value={quiero}
                        on:change={() => convertir()}>
                        {#each monedas as moneda}
                            <option>{moneda}</option>
                        {/each}
                    </select>
                </div>
            </div>
        </div>
        {#if cantidad > 0}
            <h4 class="text-center">{cantidad} {tengo} SON {total.toFixed(2)} {quiero}</h4>
        {/if}
    </div>
</div>
