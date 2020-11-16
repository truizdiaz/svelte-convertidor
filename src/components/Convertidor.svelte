<script>
    let tengo = "USD";
    let quiero = "EUR";
    let cantidad = 0;
    let total = 0;
    let monedas = ["USD", "EUR", "LIBRA"];
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
                        placeholder="1000" />
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <div class="form-group">
                    <label for="tengo">Tengo</label>
                    <select class="form-control form-control-lg" id="tengo" bind:value={tengo}>
                        {#each monedas as moneda}
                            <option>{ moneda }</option>
                        {/each}
                    </select>
                </div>
            </div>
            <div class="col-lg-6">
                <div class="form-group">
                    <label for="quiero">Quiero</label>
                    <select class="form-control form-control-lg" id="quiero" bind:value={quiero}>
                        {#each monedas as moneda}
                            <option>{ moneda }</option>
                        {/each}
                    </select>
                </div>
            </div>
        </div>
        <h4 class="text-center">
            {cantidad} {tengo} SON {total} {quiero}
        </h4>
    </div>
</div>
