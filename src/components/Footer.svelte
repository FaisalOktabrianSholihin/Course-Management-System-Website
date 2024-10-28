<script lang="ts">
    import { page } from "$app/stores";

    let isLoginPage = false;

    // Memantau perubahan halaman
    $: {
        const currentPath = $page.url.pathname;
        isLoginPage = currentPath === "/login"; // Tentukan halaman login
    }
</script>

<footer class="py-20">
    <!-- Bagian footer umum yang tidak ditampilkan di halaman login -->
    {#if !isLoginPage}
        <div class="footer-content">
            <div class="footer-section">
                <h4>E-Course</h4>
                <p>Mulai dari sekarang bersama e-course</p>
            </div>

            <div class="footer-section section-right">
                <h4>Navigasi</h4>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#courses">Courses</a></li>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>

            <div class="footer-section section-right">
                <h4>PT. Lambda Cipta Solusi</h4>
                <p>
                    Jl. Simpang Raya Langsep No.20b,<br />
                    Pisang Candi, Kec. Sukun, Kota Malang,<br />
                    Jawa Timur 65146<br />
                    +62 89667198121
                </p>
            </div>
        </div>
    {/if}

    <!-- Bagian copyright yang selalu ditampilkan -->
    <div class="copyright">© 2024 E-Course. Hak cipta dilindungi.</div>
</footer>

<style>
    footer {
        background-color: #e5f2f7;
        padding: 10px 0;
        text-align: center;
    }

    .footer-content {
        font-size: 0.9rem; /* Ukuran font keseluruhan footer */
        display: flex;
        justify-content: flex-start;
        max-width: 1200px;
        margin: 0 auto;
        padding: 0 20px;
        color: #6b6f7d;
        text-align: left;
    }

    .footer-section {
        flex: 1;
        padding: 0 20px;
    }

    .footer-section h4 {
        font-size: 1.1rem; /* Ukuran font untuk judul */
        font-weight: bold;
        margin-bottom: 10px;
        color: #000;
    }

    .footer-section p,
    .footer-section a,
    .footer-section ul li {
        font-size: 0.9rem; /* Ukuran font lebih kecil untuk isi teks */
        color: #6b6f7d;
    }

    .footer-section a {
        text-decoration: none;
        color: #000;
        font-size: 16px;
    }

    .footer-section a:hover {
        color: #007bff;
    }

    .section-right {
        margin-left: 50px;
    }

    .copyright {
        font-size: 0.8rem; /* Ukuran font lebih kecil untuk copyright */
        margin-top: 65px;
        color: #6b6f7d;
    }
</style>
