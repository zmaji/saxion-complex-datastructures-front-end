<script>
    import router from "page";
</script>

<nav class="navbar navbar-expand-lg navbar-light bg-white fixed-top border-top border-4 border-primary shadow">
    <div class="container">
        <a class="navbar-brand" on:click={() => router.redirect('/')} href="/">
            <img src="/img/saxion-logo.jpg" alt="" width="100">
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a class="nav-link" on:click={() => router.redirect('/')}>Guide</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Homes</a>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/homes')}>All homes</a></li>
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/homes/top-maintenance')}>Top maintenance</a></li>
                    </ul>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Waiting list</a>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/waiting-list')}>Waiting list</a></li>
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/waiting-list/qualified')}>Qualified client homes</a></li>
                    </ul>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Complaints</a>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/complaints')}>Complaints</a></li>
                        <li><a class="dropdown-item nav-link" on:click={() => router.redirect('/complaints/complaint-frequency')}>Complaint frequency</a></li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</nav>

<style>
    .nav-link:hover {
        cursor: pointer;
        text-decoration: none;
    }
</style>