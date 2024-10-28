<script>
    let email = "";
    let password = "";
    let showPassword = false;

    const togglePasswordVisibility = () => {
        showPassword = !showPassword;
    };
</script>

<div class="login-container">
    <div class="image-section">
        <img src="/images/loginn.png" alt="Login Image" />
    </div>

    <div class="form-section">
        <div class="form-container">
            <h2>Masuk</h2>
            <div class="form-group">
                <label for="email">Alamat Email</label>
                <input
                    type="email"
                    id="email"
                    bind:value={email}
                    placeholder="Alamat Email"
                />
            </div>
            <div class="form-group password-container">
                <label for="password">Kata Sandi</label>
                {#if showPassword}
                    <input
                        type="text"
                        id="password"
                        bind:value={password}
                        placeholder="Kata Sandi"
                    />
                {:else}
                    <input
                        type="password"
                        id="password"
                        bind:value={password}
                        placeholder="Kata Sandi"
                    />
                {/if}
            </div>
            <div class="forgot-password">Lupa Password</div>
            <button class="btn" type="submit">Masuk</button>
        </div>
    </div>
</div>

<style>
    .login-container {
        display: flex;
        height: 100vh;
        flex-wrap: nowrap; /* Menghindari pembungkusan untuk full image */
    }

    .image-section {
        flex: 1;
        background-color: #003366;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden; /* Menyembunyikan bagian gambar yang tidak terlihat */
    }

    .image-section img {
        width: 100%; /* Memastikan gambar mengambil lebar penuh */
        height: 100%; /* Memastikan gambar mengambil tinggi penuh */
        object-fit: cover; /* Memastikan gambar tetap proporsional */
    }

    .form-section {
        flex: 1;
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .form-container {
        width: 80%;
        max-width: 400px;
    }

    h2 {
        font-size: 28px;
        margin-bottom: 20px;
        color: #000;
    }

    .form-group {
        margin-bottom: 20px;
    }

    label {
        display: block;
        font-size: 16px;
        margin-bottom: 5px;
        color: #000;
    }

    input[type="email"],
    input[type="password"],
    input[type="text"] {
        width: 100%;
        padding: 10px;
        font-size: 16px;
        border: 1px solid #ddd;
        border-radius: 5px;
        background-color: #f1f1f1;
    }

    .password-container {
        position: relative;
    }

    .toggle-password {
        position: absolute;
        right: 10px;
        top: 50%;
        transform: translateY(-50%);
        cursor: pointer;
    }

    .forgot-password {
        text-align: right;
        font-size: 14px;
        color: #888;
        cursor: pointer;
        margin-top: 5px;
    }

    .btn {
        width: 100%;
        padding: 10px;
        font-size: 16px;
        color: #fff;
        background-color: #003366;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .btn:hover {
        background-color: #002244;
    }

    @media (max-width: 768px) {
        .login-container {
            flex-direction: column;
            height: auto;
        }

        .image-section,
        .form-section {
            flex: none;
            width: 100%;
            height: auto;
        }

        .form-container {
            margin-top: 20px;
        }
    }

    @media (max-width: 480px) {
        h2 {
            font-size: 24px;
        }

        .btn {
            padding: 12px;
            font-size: 18px;
        }
    }
</style>
