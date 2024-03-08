<template>
    <div class="container">
        <form>
            <div class="mb-3">
                <div class="form-label">
                    <label for="exampleInputEmail1" class="email-form">Email</label>
                    <div class="link-signup">
                        Need an account? <a href="#" class="sign-up">SIGN UP</a>
                    </div>
                </div>
                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" />
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword1" />
                <div class="form-text">10 Maximum length, at least one uppercase letter, at least one lowercase letter,
                    and at least one digit.</div>
            </div>
            <div class="mb-3">
                <a href="#" class="forget-password">Forgot Password?</a>
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    </div>
</template>

<script>
export default {

}
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

.form-label {
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
    margin-top: 0;
    float: right;
}
</style>