<script>
    // @ts-nocheck
    let showFullCurriculum = false;
    // Variable untuk data kursus
    let course = {
        title: "Framework Laravel",
        duration: "12 Jam",
        rating: 4.9,
        level: "Dasar",
        price: "Rp 100.000",
        description:
            "Laravel adalah salah satu framework PHP yang paling populer dan banyak digunakan untuk pengembangan aplikasi web. Dikenal dengan sintaksis yang elegan dan fitur-fitur canggih, Laravel menawarkan berbagai alat yang memudahkan pengembang dalam membangun aplikasi yang robust dan skalabel.",
        curriculum: [
            "Bab 1. Pengenalan Laravel",
            "Bab 2. Pemodelan Data dengan Eloquent",
            "Bab 3. Pengenalan Blade",
            "Bab 4. Relasi dalam Eloquent",
            "Bab 5. Query Builder dan Raw SQL",
            "Bab 6. Migrasi dan Seeder",
        ],
        learningPaths: [
            "Materi dan pembelajaran disajikan oleh instruktur yang berpengalaman dan mempunyai sertifikat resmi.",
            "Penilaian dilakukan melalui pre-test maupun post-test untuk mengukur pemahaman peserta.",
            "Pelatihan menyediakan kamp latihan untuk latihan mengerjakan ujian melalui kuis online.",
        ],
        totalPaths: 3,
    };
</script>

<!-- Tampilan untuk detail kursus -->
<div class="course-page">
    <main class="course-detail">
        <div class="course-image">
            <img src="/images/laravel.png" alt="Laravel" />
        </div>

        <div class="course-info">
            <div class="course-title-price">
                <h1 class="font-bold">{course.title}</h1>
                <p class="price">{course.price}</p>
            </div>
            <div class="course-meta">
                <span
                    ><i class="fas fa-clock fa-xs" style="color: deepskyblue;"
                    ></i>
                    {course.duration}</span
                >
                <span
                    ><i class="fas fa-star fa-xs" style="color: gold;"></i>
                    {course.rating}</span
                >
                <span
                    ><i class="fas fa-signal fa-xs" style="color: blue;"></i>
                    {course.level}</span
                >
            </div>
            <p>{course.description}</p>

            <h3 class="font-semibold">Rincian Kursus Laravel:</h3>
            <ul>
                {#each !showFullCurriculum ? course.curriculum.slice(0, 2) : course.curriculum as item}
                    <li>{item}</li>
                {/each}
            </ul>
            <div class="center-text">
                <hr class="mt-5 md:min-w-full" />
                <button
                    on:click={() => (showFullCurriculum = !showFullCurriculum)}
                    style="text-decoration: underline; cursor: pointer; background: none; border: none; color: #007bff;"
                >
                    {!showFullCurriculum ? "Selengkapnya" : "Lebih Sedikit"}
                </button>
            </div>

            <h3 class="font-semibold">Jalur Pembelajaran</h3>
            <ul>
                {#each course.learningPaths as path}
                    <li>
                        <i class="fas fa-check-circle" style="color: gray;"></i>
                        {path}
                    </li>
                {/each}
            </ul>
            <hr class="mt-4 md:min-w-full" />
            <p class="from-neutral-700">
                <i class="fas fa-check-circle" style="color: green;"></i>
                {course.totalPaths} Jalur pembelajaran secara total
            </p>

            <div class="buttons">
                <button class="cart">Keranjang</button>
                <button class="buy">Bayar</button>
            </div>
        </div>
    </main>
</div>

<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        background-color: #f8f9fa;
    }

    main {
        color: black;
        display: flex;
        max-width: 1200px;
        margin: 2rem auto;
        padding: 2rem;
        background-color: white;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        flex-wrap: wrap;
    }

    .course-image img {
        width: 100%;
        max-width: 300px;
        height: auto;
    }

    .course-info {
        margin-left: 2rem;
        flex: 1;
    }

    h1 {
        color: black;
        margin-bottom: 0.5rem;
        font-size: 2rem;
    }

    .course-meta span {
        margin-right: 1rem;
        color: #666;
    }

    .price {
        font-size: 1.5rem;
        font-weight: bold;
        margin-top: 1rem;
        color: #007bff;
    }

    ul {
        margin: 1rem 0;
        padding-left: 1rem;
    }

    .buttons {
        margin-top: 2rem;
    }

    .buttons button {
        padding: 0.5rem 1.5rem;
        border: none;
        border-radius: 5px;
        margin-right: 1rem;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }

    .buttons .cart {
        background-color: white;
        color: #007bff;
        border: 2px solid #007bff;
    }

    .buttons .buy {
        background-color: #007bff;
        color: white;
    }

    .buttons .cart:hover {
        background-color: #007bff;
        color: white;
    }

    .buttons .buy:hover {
        background-color: #0056b3;
    }

    .course-title-price {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .center-text {
        text-align: center;
    }

    a {
        color: #007bff;
    }

    a:hover {
        text-decoration: none;
    }

    /* Responsive Styles */
    @media (max-width: 768px) {
        main {
            flex-direction: column;
            padding: 1rem;
        }

        .course-image {
            margin-bottom: 1rem;
        }

        .course-info {
            margin-left: 0;
        }

        .buttons {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .buttons button {
            width: 100%;
            margin: 0.5rem 0;
        }
    }
</style>
