<template>
    <div class="container">
        <form>
            <h1 class="form-header">LOG IN</h1>
            <div class="mb-3">
                <div class="label-container">
                    <label for="exampleInputEmail1" class="form-label">Email</label>
                    <div class="link-signup">
                        Need an account? <RouterLink to="/signup" class="signup">SIGN UP</RouterLink>
                    </div>
                </div>
                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" />
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword1" />
                <div class="form-text">Password should have at least one uppercase letter, one lowercase letter, one
                    digit, and be between 8 and 10 characters in length.</div>
            </div>
            <div class="mb-3">
                <a href="#" class="forget-password">Forgot Password?</a>
            </div>
            <button type="submit" class="btn btn-primary" @click="login">LOG IN</button>
        </form>
    </div>
</template>

<script>
export default {
    methods: {
        login() {
            const emailInput = document.getElementById('exampleInputEmail1');
            const passwordInput = document.getElementById('exampleInputPassword1');

            const email = emailInput.value;
            const password = passwordInput.value;

            if (!email || !password) {
                alert('Please enter your email and password.');

                emailInput.value = ''; // Clear email input
                passwordInput.value = ''; // Clear password input

                return;
            }

            const savedData = localStorage.getItem('signupData');

            if (savedData) {
                const signupData = JSON.parse(savedData);

                if (email === signupData.email && password === signupData.password) {
                    alert('Logged in successfully!');
                    // Implement your logic for successful login (e.g., redirect to a new page)
                    this.$router.push("/dashboard");
                    return;
                } else {
                    alert('Invalid email or password.');
                    passwordInput.value = ''; // Clear password input
                }
            } else {
                alert('Please sign up first.');
            }
        }
    }
};
</script>

<style scoped>
.container {
    border: 2px solid #28a745;
    background-color: var(--vt-c-dark-green-2);
    border-radius: 20px;
    padding: 1.5rem;
    max-width: 400px;
    margin: 0 auto;
}

.form-text {
    color: #fff;
}

.form-header {
    color: #138496;
    display: flex;
    justify-content: center;
    margin-bottom: 10%;
}

.label-container {
    display: flex;
    align-items: center;
    color: #fff;
}

.link-signup {
    margin-left: auto;
}

.link-signup .sign-up {
    color: #17a2b8;
    text-decoration: none;
    transition: color 0.4s, font-weight 0.4s;
}

.link-signup .sign-up:hover {
    color: #138496;
    font-weight: bold;
}

.forget-password {
    color: #17a2b8;
    text-decoration: none;
    transition: color 0.4s, font-weight 0.4s;
}

.forget-password:hover {
    color: #138496;
    font-weight: bold;
}

.btn-primary {
    background-color: #3da385;
    margin-top: 0;
    float: right;
}

.text-btn-primary {
    color: #fff;
}
</style>