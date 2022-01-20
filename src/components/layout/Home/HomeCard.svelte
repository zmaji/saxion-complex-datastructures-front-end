<script>
    export let home = {};
</script>

<div class="col-12 col-md-6 col-lg-4 p-3">
    <div class="bg-white rounded border border-primary p-3">
        <h4>Home: {home.homeID}</h4>
        <p>AddressX: {home.addressX}</p>
        <p>AddressY: {home.addressY}</p>
        <p>Rent: € {home.rent}</p>
        <p>NrOfRooms: {home.nrOfRooms}</p>
        <p>Garden: {home.garden}</p>
    </div>
</div>