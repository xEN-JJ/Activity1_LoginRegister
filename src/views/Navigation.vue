<template>
    <header>
        <div class="nav-container">
            <nav class="nav">
                <a class="nav-link active" aria-current="page" href="#">PLMS</a>
                <a class="nav-link" href="../views/HomeView.vue">
                    <RouterLink to="/home">Home</RouterLink>
                </a>
                <a class="nav-link" href="../views/AboutView.vue">
                    <RouterLink to="/about">About</RouterLink>
                </a>

                <a class="nav-link disabled" aria-disabled="true">PORTERIAN LIBRARY MANAGEMENT SYSTEM</a>

                    <ul class="navbar-nav ml-auto">
                        <li class="nav-item">
                            <RouterLink to="/login" class="nav-link-authentication">Login</RouterLink>
                        </li>
                        <li class="nav-item">
                            <RouterLink to="/signup" class="nav-link-authentication">Sign Up</RouterLink>
                        </li>
                    </ul>
            </nav>
        </div>
    </header>
    <RouterView />
</template>
  
<script>

// Your script code
</script>
  
<style scoped>
header {
    /* Existing styles */
    margin-top: 0;
    /* Remove or adjust as needed */
}

.nav-container {
    display: flex;
    background-color: var(--vt-c-black);
    padding: 1rem;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--vt-c-white);
}

.nav-link {
    text-decoration: none;
    color: var(--vt-c-text-light-1);
    transition: 0.4s;
    padding: 3px;
}

.nav-link.active {
    font-weight: bold;
}

.nav-link:hover {
    background-color: var(--vt-c-indigo);
}

.nav-link.disabled {
    color: var(--vt-c-text-dark-2);
}

.nav-link-authentication {
    color: var(--vt-c-white);
    text-decoration: none;
    transition: 0.4s;
}

.nav-link-authentication:hover {
    color: var(--vt-c-indigo);
}

@media (min-width: 1024px) {
    header {
        /* Existing styles */
        margin-top: 0;
        /* Remove or adjust as needed */
    }

    .nav-container {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .nav {
        max-width: 1280px;
        margin: 0 auto;
        padding: 0 2rem;
    }
}
</style>