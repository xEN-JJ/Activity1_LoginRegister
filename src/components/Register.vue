<template>
    <div class="container">
        <form>
            <h1 class="form-header">SIGN UP</h1>
            <div class="mb-3">
                <div class="label-container">
                    <label for="exampleInputEmail1" class="form-label">Email</label>
                    <div class="link-signup">
                        Already have an account? <RouterLink to="/login" class="signup">LOG IN</RouterLink>
                    </div>
                </div>
                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" />
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword1" />
                <div class="form-text">Password should have at least one uppercase letter, one lowercase letter, one digit, and be between 8 and 10 characters in length.</div>
            </div>
            <div class="mb-3">
                <div class="label-container">
                    <input type="checkbox" id="agreeToConditions" class="form-checkbox" />
                    <label for="agreeToConditions" class="form-label">Agree to the conditions</label>
                </div>
            </div>
            <button type="submit" class="btn btn-primary" @click="saveSignUp">SIGN UP</button>
        </form>
    </div>
</template>

<script>
export default {
    methods: {
        saveSignUp() {
            const emailInput = document.getElementById('exampleInputEmail1');
            const passwordInput = document.getElementById('exampleInputPassword1');
            const agreeToConditionsInput = document.getElementById('agreeToConditions');

            const email = emailInput.value;
            const password = passwordInput.value;
            const agreeToConditions = agreeToConditionsInput.checked;

            if (!email || !password || !agreeToConditions) {
                alert('Please fill in all the required fields and agree to the conditions.');

                emailInput.value = ''; // Clear email input
                passwordInput.value = ''; // Clear password input
                agreeToConditionsInput.checked = false; // Uncheck agreeToConditions checkbox

                return;
            }

            const passwordPattern = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,10}$/;
            // The pattern requires at least one digit, one lowercase letter, one uppercase letter, and a length between 8 and 10 characters.

            if (!passwordPattern.test(password)) {
                alert('Password should have at least one uppercase letter, one lowercase letter, one digit, and be between 8 and 10 characters in length.');
                passwordInput.value = ''; // Clear password input
                return;
            }

            const signupData = {
                email,
                password
            };

            localStorage.setItem('signupData', JSON.stringify(signupData));
            alert('Signup data saved!');
            this.$router.push('/login');
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
    padding-bottom: 10px;
    /* Add padding bottom here */
}

.label-container input[type="checkbox"],
.label-container input[type="radio"] {
    margin-right: 8px;
    /* Add some margin between the input and label */
}

.link-signup {
    margin-left: auto;
}

.link-signup .signup {
    color: #17a2b8;
    text-decoration: none;
    transition: color 0.4s, font-weight 0.4s;
}

.link-signup .signup:hover {
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

.btn-primary:hover {
    font-weight: bold;
}
</style>