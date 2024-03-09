<template>
    <header>
        <div class="nav-container">
            <nav class="nav">
                <div class="left-side">
                    <div class="nav-links">
                        <a class="nav-link" href="../views/HomeView.vue">
                            <RouterLink to="/home">Home</RouterLink>
                        </a>
                        <a class="nav-link" href="../views/AboutView.vue">
                            <RouterLink to="/about">About</RouterLink>
                        </a>
                    </div>
                    <div class="nav-link-disabled">
                        <span class="small">PORTERIAN LIBRARY MANAGEMENT SYSTEM</span>
                    </div>
                </div>

                <div class="right-side">
                    <div class="nav-links">
                        <RouterLink to="/login" class="nav-link-authentication">Login</RouterLink>
                        <RouterLink to="/signup" class="nav-link-authentication" style="margin-right: 1rem;">Sign Up
                        </RouterLink>
                    </div>
                </div>
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
    margin-top: 0;
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
    padding: 20px;
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

.left-side {
    display: flex;
    align-items: center;
}

.right-side {
    display: flex;
    align-items: center;
    margin-right: 20px;
}

.nav-links {
    display: flex;
}

.nav-links .nav-link-authentication {
    margin-left: 1rem;
}

.nav-link-disabled {
    color: var(--vt-c-text-dark-2);
    font-size: 0.8rem;
    text-align: center;
}

.nav-link-disabled .small {
    display: block;
    font-size: 0.8rem;
    font-weight: bold;
    text-transform: uppercase;
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

    .left-side {
        flex-grow: 1;
    }

    .right-side {
        flex-grow: 1;
        display: flex;
        justify-content: flex-end;
    }

    .right-side .nav-links {
        margin-left: 1rem;
    }
}
</style>