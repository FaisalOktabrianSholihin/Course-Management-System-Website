<script>
    import Step from "./Step.svelte";
    import Carousel from "./Carousel.svelte";

    // @ts-ignore
    function goToCourseDetail(courseName) {
        window.location.href = `/${courseName}`;
    }

    let steps = [
        {
            name: "Smoljames Store",
            icon: "fa-solid fa-cart-shopping",
            description:
                "Smoljames Store is a merchanising store created with Next.js, Commerce.js & Stripe! Commerce.js is a CMS for managing project and Stripe is used for all transaction handling.",
        },
        {
            name: "Utlimate Todos",
            icon: "fa-solid fa-list-check",
            description:
                "Test for model robustness with customized test profiles and receive exhaustive reporting on the performance and potential vulnerabilities of your model.",
        },
        {
            name: "Pokédex",
            icon: "fa-solid fa-diagram-project",
            description:
                "Augment your datasets with our filters and dataset manipulations to ensure your models are trained on the highest quality datasets (coming soon).",
        },
    ];
    let benefits = [
        {
            metric: "10x",
            name: "a self taught developer",
            description:
                "I taught myself to code using free online resources and absolutely fell in love with the creativity and problem solving that is involved in developing and engineering innovative new online experiences. Starting of with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much much more.",
        },
        {
            name: "a product design & UX finatic",
            description:
                "Carefully crafting and designing amazing user experiences allows me to express and experiment with every morsel of creativity I have. I love the challenge of learning new design concepts and enabling users with amazing online experiences.",
        },
        {
            name: "an excellent communicator",
            description:
                "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
        },
    ];

    let images = [
        { src: "images/hero.png", alt: "Hero 1" },
        { src: "images/hero1.png", alt: "Hero 2" },
        { src: "images/hero2.png", alt: "Hero 3" },
    ];
</script>

<main class="flex flex-col flex-1 p-4">
    <!-- <section
        id="introPage"
        class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
    >
        <div
            class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        >
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                E-course <span class="poppins text-blue-900">Lambda</span>
                Solusi
                <br />Full Stack
                <span class="poppins text-blue-900">Svelte</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                Ayo <span class="text-blue-900"> latih skill</span> bersama e-course
                yang akan menemani harimu menjadi lebih indah dengan lagu Sal Priadi
            </p>
            <button
                class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950"
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-blue-900 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Info Lebih Lanjut</h4>
            </button>
        </div>
        <Carousel {images} />
    </section> -->

    <section id="hero">
        <Carousel {images} />
    </section>

    <section class="lg:py-10 flex flex-col gap-10" id="kelebihan">
        <div class="flex flex-col gap-2 text-center">
            <h3 class="text-2xl font-bold">
                Kembangkan Skill Bersama <span class="poppins text-blue-900"
                    >E-Course</span
                >
            </h3>
        </div>

        <div class="flex justify-center gap-10 flex-wrap">
            <div
                class="card flex flex-col items-center text-center border border-gray-200 rounded-lg shadow-md p-5"
            >
                <img
                    src="images/keunggulan.png"
                    alt="Join Us"
                    class="w-32 h-32 mb-4"
                />
                <p class="font-semibold text-md">
                    Telah diikuti oleh ribuan peserta
                </p>
                <p class="text-sm text-gray-500">untuk belajar bersama</p>
            </div>

            <div
                class="card flex flex-col items-center text-center border border-gray-200 rounded-lg shadow-md p-5"
            >
                <img
                    src="images/keunggulan.png"
                    alt="Join Us"
                    class="w-32 h-32 mb-4"
                />
                <p class="font-semibold text-md">
                    Telah diikuti oleh ribuan peserta
                </p>
                <p class="text-sm text-gray-500">untuk belajar bersama</p>
            </div>

            <div
                class="card flex flex-col items-center text-center border border-gray-200 rounded-lg shadow-md p-5"
            >
                <img
                    src="images/keunggulan.png"
                    alt="Join Us"
                    class="w-32 h-32 mb-4"
                />
                <p class="font-semibold text-md">
                    Telah diikuti oleh ribuan peserta
                </p>
                <p class="text-sm text-gray-500">untuk belajar bersama</p>
            </div>

            <div
                class="card flex flex-col items-center text-center border border-gray-200 rounded-lg shadow-md p-5"
            >
                <img
                    src="images/keunggulan.png"
                    alt="Join Us"
                    class="w-32 h-32 mb-4"
                />
                <p class="font-semibold text-md">
                    Telah diikuti oleh ribuan peserta
                </p>
                <p class="text-sm text-gray-500">untuk belajar bersama</p>
            </div>
        </div>
    </section>

    <section id="kursus">
        <div class="flex justify-between items-center">
            <h3 class="text-2xl font-bold">Kursus yang dapat dipelajari</h3>
            <div class="relative">
                <input
                    type="text"
                    placeholder="Cari..."
                    class="border border-gray-300 rounded-xl py-2 pl-8 pr-4 focus:outline-none focus:ring focus:ring-blue-900"
                />
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="absolute left-2 top-1/2 transform -translate-y-1/2 h-5 w-5 text-gray-400"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                >
                    <path
                        fill-rule="evenodd"
                        d="M12.9 14.32a8 8 0 111.41-1.41l4.3 4.3a1 1 0 01-1.42 1.42l-4.3-4.3zM8 14a6 6 0 100-12 6 6 0 000 12z"
                        clip-rule="evenodd"
                    />
                </svg>
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-4 gap-6 mt-8">
            <button
                class="border rounded-lg shadow-md p-4 text-center cursor-pointer"
                on:click={() => goToCourseDetail("detailkursus")}
            >
                <img
                    src="images/laravel.png"
                    alt="Framework Laravel"
                    class="w-full h-32 object-cover rounded-md mb-4"
                />
                <div class="text-left">
                    <div class="flex items-center gap-2 mb-2">
                        <img
                            src="images/google.png"
                            alt="Google"
                            class="w-6 h-6"
                        />
                        <span class="text-sm">Google</span>
                    </div>
                    <h4 class="font-semibold text-md">Framework Laravel</h4>
                    <p class="text-sm text-gray-500">Sertifikat Profesional</p>
                </div>
            </button>
            <button
                class="border rounded-lg shadow-md p-4 text-center cursor-pointer"
                on:click={() => goToCourseDetail("detailkursus")}
            >
                <img
                    src="images/laravel.png"
                    alt="Framework Laravel"
                    class="w-full h-32 object-cover rounded-md mb-4"
                />
                <div class="text-left">
                    <div class="flex items-center gap-2 mb-2">
                        <img
                            src="images/google.png"
                            alt="Google"
                            class="w-6 h-6"
                        />
                        <span class="text-sm">Google</span>
                    </div>
                    <h4 class="font-semibold text-md">Framework Laravel</h4>
                    <p class="text-sm text-gray-500">Sertifikat Profesional</p>
                </div>
            </button>
            <button
                class="border rounded-lg shadow-md p-4 text-center cursor-pointer"
                on:click={() => goToCourseDetail("detailkursus")}
            >
                <img
                    src="images/laravel.png"
                    alt="Framework Laravel"
                    class="w-full h-32 object-cover rounded-md mb-4"
                />
                <div class="text-left">
                    <div class="flex items-center gap-2 mb-2">
                        <img
                            src="images/google.png"
                            alt="Google"
                            class="w-6 h-6"
                        />
                        <span class="text-sm">Google</span>
                    </div>
                    <h4 class="font-semibold text-md">Framework Laravel</h4>
                    <p class="text-sm text-gray-500">Sertifikat Profesional</p>
                </div>
            </button>
            <button
                class="border rounded-lg shadow-md p-4 text-center cursor-pointer"
                on:click={() => goToCourseDetail("detailkursus")}
            >
                <img
                    src="images/laravel.png"
                    alt="Framework Laravel"
                    class="w-full h-32 object-cover rounded-md mb-4"
                />
                <div class="text-left">
                    <div class="flex items-center gap-2 mb-2">
                        <img
                            src="images/google.png"
                            alt="Google"
                            class="w-6 h-6"
                        />
                        <span class="text-sm">Google</span>
                    </div>
                    <h4 class="font-semibold text-md">Framework Laravel</h4>
                    <p class="text-sm text-gray-500">Sertifikat Profesional</p>
                </div>
            </button>
        </div>
        <div class="flex text-left mt-6">
            <button
                class="border border-blue-900 text-blue-900 px-4 py-2 rounded-md hover:bg-blue-900 hover:text-white transition"
            >
                Tampilkan lebih banyak
            </button>
        </div>
    </section>
</main>
