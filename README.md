<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Little Bunny Crafting</title>
    <!-- Load Tailwind CSS CDN --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Pacifico and Inter fonts --><link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Pacifico&display=swap" rel="stylesheet">
    
    <style>
        /* Custom Fonts */
        .font-pacifico { font-family: 'Pacifico', cursive; }
        .font-inter { font-family: 'Inter', sans-serif; }

        /* Slow-motion bounce for hero icon */
        @keyframes bounce-slow {
            0%, 100% { transform: translateY(-5%); }
            50% { transform: translateY(0); }
        }
        .animate-bounce-slow {
            animation: bounce-slow 4s infinite ease-in-out;
        }
    </style>
</head>
<body class="font-inter min-h-screen bg-pink-50 text-gray-800 antialiased">

    <!-- Rabbit/Heart SVG Icons (Reusable) --><template id="logo-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="h-10 w-10 mr-3 text-pink-700">
            <!-- Bunny Body --><path class="fill-pink-200 stroke-pink-700" d="M18.87 9.17c-1.07-1.1-2.45-2-4.43-2.61a1.27 1.27 0 0 0-1.08.31c-.5.42-1.19.42-1.69 0a1.27 1.27 0 0 0-1.08-.31c-1.98.61-3.36 1.51-4.43 2.61C4.3 10.3 3 12.2 3 14c0 1.8 1.3 3.7 3.17 4.83l.53.33c.9.56 2.0 .94 3.13 1.09a7.35 7.35 0 0 0 4.34 0c1.13-.15 2.23-.53 3.13-1.09l.53-.33C19.7 17.7 21 15.8 21 14c0-1.8-1.3-3.7-3.13-4.83Z"/>
            <!-- Ears --><path class="stroke-pink-700" d="M16 9c.14-.62.27-1.3.4-2l.5-3.5"/>
            <path class="stroke-pink-700" d="M8 9c-.14-.62-.27-1.3-.4-2l-.5-3.5"/>
            <!-- Heart detail --><path class="fill-red-400 stroke-red-500" stroke-width="0.5" d="M12 18l-1-1a3 3 0 0 1 4 0l-1 1z"/>
        </svg>
    </template>
    
    <template id="instagram-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4 mr-2">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
            <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
            <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
        </svg>
    </template>

    <template id="heart-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-6 h-6 mr-2 fill-pink-600/10">
            <path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/>
        </svg>
    </template>

    <template id="rabbit-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-16 h-16 mx-auto text-pink-600 mb-4 animate-bounce-slow">
            <path d="M18.87 9.17c-1.07-1.1-2.45-2-4.43-2.61a1.27 1.27 0 0 0-1.08.31c-.5.42-1.19.42-1.69 0a1.27 1.27 0 0 0-1.08-.31c-1.98.61-3.36 1.51-4.43 2.61C4.3 10.3 3 12.2 3 14c0 1.8 1.3 3.7 3.17 4.83l.53.33c.9.56 2.0 .94 3.13 1.09a7.35 7.35 0 0 0 4.34 0c1.13-.15 2.23-.53 3.13-1.09l.53-.33C19.7 17.7 21 15.8 21 14c0-1.8-1.3-3.7-3.13-4.83Z"/>
            <path d="M16 9c.14-.62.27-1.3.4-2l.5-3.5"/>
            <path d="M8 9c-.14-.62-.27-1.3-.4-2l-.5-3.5"/>
        </svg>
    </template>

    <!-- Header --><header class="sticky top-0 z-10 bg-white shadow-lg">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#" class="flex items-center text-3xl font-pacifico text-pink-600 hover:text-pink-700 transition duration-300" id="header-logo-container">
                <!-- Logo will be inserted here by JS -->Little Bunny Crafting
            </a>
            <nav class="space-x-4 flex items-center">
                <a href="#about" class="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">About</a>
                <a href="#gallery" class="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">Gallery</a>
                <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="bg-pink-500 text-white px-4 py-2 rounded-full shadow-md hover:bg-pink-600 transition duration-300 text-sm flex items-center" id="instagram-link-header">
                    <!-- Instagram icon will be inserted here by JS -->Follow
                </a>
            </nav>
        </div>
    </header>

    <main>
        <!-- Hero Section --><section class="py-16 md:py-24 bg-pink-100/50 relative overflow-hidden">
            <!-- Decorative background image --><div class="absolute inset-0 z-0 opacity-20">
                <img
                    src="https://image.pollinations.ai/prompt/pastel%20crafting%20background%20with%20blurred%20bunnies%20and%20yarn%2C%20soft%20focus%2C%20dreamy?width=1920&height=1080&seed=bg1"
                    alt="Soft crafting background"
                    class="w-full h-full object-cover"
                />
            </div>
            <div class="container mx-auto px-4 text-center relative z-10">
                <div class="max-w-3xl mx-auto">
                    <div id="hero-rabbit-icon-container">
                        <!-- Rabbit icon will be inserted here by JS --></div>
                    <h1 class="text-5xl md:text-6xl font-extrabold text-pink-700 leading-tight mb-4 drop-shadow-md">
                        Handmade Happiness, One Stitch at a Time
                    </h1>
                    <p class="text-xl text-gray-700 mb-8 max-w-xl mx-auto drop-shadow-sm">
                        Welcome to our cozy corner of creativity. We specialize in adorable, custom-made crafts inspired by all things cute and fluffy!
                    </p>
                    <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="inline-block bg-pink-500 text-white text-xl font-semibold px-8 py-3 rounded-xl shadow-lg hover:bg-pink-600 transform hover:scale-105 transition duration-300 ease-in-out">
                        See Our Latest Posts on Instagram
                    </a>
                </div>
            </div>
        </section>

        <!-- About Section --><section id="about" class="py-16 md:py-20">
            <div class="container mx-auto px-4 max-w-5xl">
                <h2 class="text-4xl font-bold text-center text-pink-600 mb-10">Our Story & Mission</h2>
                <div class="flex flex-col md:flex-row items-center space-y-8 md:space-y-0 md:space-x-12 bg-white p-6 md:p-10 rounded-2xl shadow-xl">
                    <div class="md:w-1/2">
                        <img
                            src="https://image.pollinations.ai/prompt/whimsical%20crafting%20desk%20with%20yarn%20balls%2C%20crochet%20hooks%2C%20and%20a%20tiny%20amigurumi%20bunny%2C%20pastel%20lighting%2C%20soft%20focus?width=600&height=400&seed=about1"
                            alt="A whimsical crafting setup"
                            class="rounded-xl shadow-lg w-full h-auto object-cover"
                        />
                    </div>
                    <div class="md:w-1/2 text-lg text-gray-700 space-y-4">
                        <p>
                            **Little Bunny Crafting** started as a simple, heartfelt hobby. It quickly grew into a passion for creating personalized, heartwarming gifts. Every item is made with love and the utmost attention to detail.
                        </p>
                        <p>
                            We believe that a handmade gift carries a piece of the maker's heart. By focusing on sustainable materials and gentle designs, we aim to bring joy and a little bit of magic into your home.
                        </p>
                        <div class="flex items-center text-pink-600 font-semibold pt-2" id="about-heart-icon-container">
                            <!-- Heart icon will be inserted here by JS -->Handmade with Love, Always.
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gallery Section --><section id="gallery" class="py-16 md:py-20 bg-pink-50">
            <div class="container mx-auto px-4">
                <h2 class="text-4xl font-bold text-center text-pink-600 mb-12">Latest Creations</h2>
                
                <div id="gallery-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
                    <!-- Gallery cards will be dynamically inserted here by JS --></div>
            </div>
        </section>
    </main>

    <!-- Footer --><footer id="contact" class="bg-pink-700 text-white py-12">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl font-bold mb-4">Connect with the Bunny!</h2>
            <p class="text-pink-200 mb-6">For custom orders or collaborations, join our crafting community.</p>

            <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="inline-flex items-center bg-pink-500 text-white font-semibold px-6 py-3 rounded-full shadow-xl hover:bg-pink-400 transition duration-300" id="instagram-link-footer">
                <!-- Instagram icon will be inserted here by JS -->@little_bunny_crafting
            </a>

            <div class="mt-8 pt-6 border-t border-pink-600">
                <p class="text-sm text-pink-300">&copy; 2024 Little Bunny Crafting. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript for dynamic content, icon injection, and gallery generation --><script>
        document.addEventListener('DOMContentLoaded', () => {
            const INSTAGRAM_LINK = "https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp";

            const CRAFT_ITEMS = [
                { id: 1, title: "Amigurumi Bunny", category: "Crochet", description: "A soft, plush companion, handcrafted with premium yarn. Perfect for snuggling.", color: "bg-purple-100 text-purple-700", imageUrl: `https://image.pollinations.ai/prompt/adorable%20amigurumi%20bunny%20toy%2C%20pastel%20pink%20and%20white%20yarn%2C%20sitting%20on%20a%20soft%20blanket%2C%20studio%20lighting?width=600&height=450&seed=craft1` },
                { id: 2, title: "Custom Greeting Cards", category: "Papercraft", description: "Intricate, layered designs for birthdays and special occasions.", color: "bg-red-100 text-red-700", imageUrl: `https://image.pollinations.ai/prompt/cute%20handmade%20greeting%20card%2C%20bunny%20theme%2C%20layered%20paper%20craft%2C%20pastel%20colors%2C%20close-up?width=600&height=450&seed=craft2` },
                { id: 3, title: "Wool Knit Scarves", category: "Knitting", description: "Cozy hand-knitted scarf made from organic, hypoallergenic wool blend.", color: "bg-green-100 text-green-700", imageUrl: `https://image.pollinations.ai/prompt/soft%20knitted%20wool%20scarf%2C%20pastel%20mint%20green%2C%20draped%20over%20a%20wooden%20chair%2C%20cozy%20atmosphere?width=600&height=450&seed=craft3` },
                { id: 4, title: "Floppy Ear Headbands", category: "Accessory", description: "Fun and floppy accessory, perfect for costume or daily whimsy.", color: "bg-yellow-100 text-yellow-700", imageUrl: `https://image.pollinations.ai/prompt/cute%20crochet%20bunny%20ear%20headband%2C%20worn%20by%20a%20child%20from%20behind%2C%20playing%20in%20a%20garden%2C%20soft%20sunlight?width=600&height=450&seed=craft4` },
                { id: 5, title: "Floral Hoop Art", category: "Embroidery", description: "Delicate stitched wall art with detailed floral and bunny motifs.", color: "bg-blue-100 text-blue-700", imageUrl: `https://image.pollinations.ai/prompt/intricate%20floral%20embroidery%20hoop%20art%2C%20with%20small%20bunnies%20among%20flowers%2C%20pastel%20threads%2C%20close-up%20texture?width=600&height=450&seed=craft5` },
                { id: 6, title: "Beginner Crochet Kits", category: "DIY Kit", description: "Everything you need to make your first tiny plushie!", color: "bg-cyan-100 text-cyan-700", imageUrl: `https://image.pollinations.ai/prompt/DIY%20crochet%20kit%20for%20beginners%2C%20with%20pastel%20yarn%2C%20crochet%20hook%2C%20and%20instructions%2C%20flat%20lay%2C%20cozy%20setting?width=600&height=450&seed=craft6` },
            ];

            // --- Icon Injection Function ---
            const injectIcon = (templateId, targetId) => {
                const template = document.getElementById(templateId);
                const target = document.getElementById(targetId);
                if (template && target) {
                    target.prepend(template.content.cloneNode(true));
                }
            };
            
            // Inject all necessary icons
            injectIcon('logo-svg', 'header-logo-container');
            injectIcon('rabbit-icon-svg', 'hero-rabbit-icon-container');
            injectIcon('heart-icon-svg', 'about-heart-icon-container');
            
            // Inject Instagram icons (must remove existing text first)
            const instagramHeaderLink = document.getElementById('instagram-link-header');
            if (instagramHeaderLink) {
                 instagramHeaderLink.prepend(document.getElementById('instagram-icon-svg').content.cloneNode(true));
            }
            const instagramFooterLink = document.getElementById('instagram-link-footer');
            if (instagramFooterLink) {
                 instagramFooterLink.prepend(document.getElementById('instagram-icon-svg').content.cloneNode(true));
            }


            // --- Gallery Rendering Function ---
            const galleryContainer = document.getElementById('gallery-container');

            CRAFT_ITEMS.forEach(item => {
                const card = document.createElement('div');
                card.className = "bg-white rounded-2xl shadow-xl overflow-hidden cursor-pointer transform hover:scale-[1.03] transition duration-300 ring-4 ring-transparent hover:ring-pink-300";

                card.innerHTML = `
                    <img
                        src="${item.imageUrl}"
                        alt="${item.title}"
                        class="w-full h-56 object-cover object-center"
                        onerror="this.onerror=null; this.src='https://placehold.co/600x450/cccccc/333333?text=Image+Not+Found'"
                    />
                    <div class="p-6">
                        <span class="inline-block mb-3 px-4 py-1 text-xs font-semibold ${item.color} rounded-full">
                            ${item.category}
                        </span>
                        <h3 class="text-2xl font-semibold text-pink-700 mb-2">${item.title}</h3>
                        <p class="text-gray-600 text-sm">${item.description}</p>
                    </div>
                `;
                galleryContainer.appendChild(card);
            });
        });
    </script>
</body>
</html>

        </svg>
    </template>
    
    <template id="instagram-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4 mr-2">
            <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
            <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
            <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
        </svg>
    </template>

    <template id="heart-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-6 h-6 mr-2 fill-pink-600/10">
            <path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/>
        </svg>
    </template>

    <template id="rabbit-icon-svg">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-16 h-16 mx-auto text-pink-600 mb-4 animate-bounce-slow">
            <path d="M18.87 9.17c-1.07-1.1-2.45-2-4.43-2.61a1.27 1.27 0 0 0-1.08.31c-.5.42-1.19.42-1.69 0a1.27 1.27 0 0 0-1.08-.31c-1.98.61-3.36 1.51-4.43 2.61C4.3 10.3 3 12.2 3 14c0 1.8 1.3 3.7 3.17 4.83l.53.33c.9.56 2.0 .94 3.13 1.09a7.35 7.35 0 0 0 4.34 0c1.13-.15 2.23-.53 3.13-1.09l.53-.33C19.7 17.7 21 15.8 21 14c0-1.8-1.3-3.7-3.13-4.83Z"/>
            <path d="M16 9c.14-.62.27-1.3.4-2l.5-3.5"/>
            <path d="M8 9c-.14-.62-.27-1.3-.4-2l-.5-3.5"/>
        </svg>
    </template>

    <!-- Header --><header class="sticky top-0 z-10 bg-white shadow-lg">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#" class="flex items-center text-3xl font-pacifico text-pink-600 hover:text-pink-700 transition duration-300" id="header-logo-container">
                <!-- Logo will be inserted here by JS -->Little Bunny Crafting
            </a>
            <nav class="space-x-4 flex items-center">
                <a href="#about" class="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">About</a>
                <a href="#gallery" class="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">Gallery</a>
                <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="bg-pink-500 text-white px-4 py-2 rounded-full shadow-md hover:bg-pink-600 transition duration-300 text-sm flex items-center" id="instagram-link-header">
                    <!-- Instagram icon will be inserted here by JS -->Follow
                </a>
            </nav>
        </div>
    </header>

    <main>
        <!-- Hero Section --><section class="py-16 md:py-24 bg-pink-100/50 relative overflow-hidden">
            <!-- Decorative background image --><div class="absolute inset-0 z-0 opacity-20">
                <img
                    src="https://image.pollinations.ai/prompt/pastel%20crafting%20background%20with%20blurred%20bunnies%20and%20yarn%2C%20soft%20focus%2C%20dreamy?width=1920&height=1080&seed=bg1"
                    alt="Soft crafting background"
                    class="w-full h-full object-cover"
                />
            </div>
            <div class="container mx-auto px-4 text-center relative z-10">
                <div class="max-w-3xl mx-auto">
                    <div id="hero-rabbit-icon-container">
                        <!-- Rabbit icon will be inserted here by JS --></div>
                    <h1 class="text-5xl md:text-6xl font-extrabold text-pink-700 leading-tight mb-4 drop-shadow-md">
                        Handmade Happiness, One Stitch at a Time
                    </h1>
                    <p class="text-xl text-gray-700 mb-8 max-w-xl mx-auto drop-shadow-sm">
                        Welcome to our cozy corner of creativity. We specialize in adorable, custom-made crafts inspired by all things cute and fluffy!
                    </p>
                    <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="inline-block bg-pink-500 text-white text-xl font-semibold px-8 py-3 rounded-xl shadow-lg hover:bg-pink-600 transform hover:scale-105 transition duration-300 ease-in-out">
                        See Our Latest Posts on Instagram
                    </a>
                </div>
            </div>
        </section>

        <!-- About Section --><section id="about" class="py-16 md:py-20">
            <div class="container mx-auto px-4 max-w-5xl">
                <h2 class="text-4xl font-bold text-center text-pink-600 mb-10">Our Story & Mission</h2>
                <div class="flex flex-col md:flex-row items-center space-y-8 md:space-y-0 md:space-x-12 bg-white p-6 md:p-10 rounded-2xl shadow-xl">
                    <div class="md:w-1/2">
                        <img
                            src="https://image.pollinations.ai/prompt/whimsical%20crafting%20desk%20with%20yarn%20balls%2C%20crochet%20hooks%2C%20and%20a%20tiny%20amigurumi%20bunny%2C%20pastel%20lighting%2C%20soft%20focus?width=600&height=400&seed=about1"
                            alt="A whimsical crafting setup"
                            class="rounded-xl shadow-lg w-full h-auto object-cover"
                        />
                    </div>
                    <div class="md:w-1/2 text-lg text-gray-700 space-y-4">
                        <p>
                            **Little Bunny Crafting** started as a simple, heartfelt hobby. It quickly grew into a passion for creating personalized, heartwarming gifts. Every item is made with love and the utmost attention to detail.
                        </p>
                        <p>
                            We believe that a handmade gift carries a piece of the maker's heart. By focusing on sustainable materials and gentle designs, we aim to bring joy and a little bit of magic into your home.
                        </p>
                        <div class="flex items-center text-pink-600 font-semibold pt-2" id="about-heart-icon-container">
                            <!-- Heart icon will be inserted here by JS -->Handmade with Love, Always.
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Gallery Section --><section id="gallery" class="py-16 md:py-20 bg-pink-50">
            <div class="container mx-auto px-4">
                <h2 class="text-4xl font-bold text-center text-pink-600 mb-12">Latest Creations</h2>
                
                <div id="gallery-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
                    <!-- Gallery cards will be dynamically inserted here by JS --></div>
            </div>
        </section>
    </main>

    <!-- Footer --><footer id="contact" class="bg-pink-700 text-white py-12">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl font-bold mb-4">Connect with the Bunny!</h2>
            <p class="text-pink-200 mb-6">For custom orders or collaborations, join our crafting community.</p>

            <a href="https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp" target="_blank" rel="noopener noreferrer" class="inline-flex items-center bg-pink-500 text-white font-semibold px-6 py-3 rounded-full shadow-xl hover:bg-pink-400 transition duration-300" id="instagram-link-footer">
                <!-- Instagram icon will be inserted here by JS -->@little_bunny_crafting
            </a>

            <div class="mt-8 pt-6 border-t border-pink-600">
                <p class="text-sm text-pink-300">&copy; 2024 Little Bunny Crafting. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript for dynamic content, icon injection, and gallery generation --><script>
        document.addEventListener('DOMContentLoaded', () => {
            const INSTAGRAM_LINK = "https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp";

            const CRAFT_ITEMS = [
                { id: 1, title: "Amigurumi Bunny", category: "Crochet", description: "A soft, plush companion, handcrafted with premium yarn. Perfect for snuggling.", color: "bg-purple-100 text-purple-700", imageUrl: `https://image.pollinations.ai/prompt/adorable%20amigurumi%20bunny%20toy%2C%20pastel%20pink%20and%20white%20yarn%2C%20sitting%20on%20a%20soft%20blanket%2C%20studio%20lighting?width=600&height=450&seed=craft1` },
                { id: 2, title: "Custom Greeting Cards", category: "Papercraft", description: "Intricate, layered designs for birthdays and special occasions.", color: "bg-red-100 text-red-700", imageUrl: `https://image.pollinations.ai/prompt/cute%20handmade%20greeting%20card%2C%20bunny%20theme%2C%20layered%20paper%20craft%2C%20pastel%20colors%2C%20close-up?width=600&height=450&seed=craft2` },
                { id: 3, title: "Wool Knit Scarves", category: "Knitting", description: "Cozy hand-knitted scarf made from organic, hypoallergenic wool blend.", color: "bg-green-100 text-green-700", imageUrl: `https://image.pollinations.ai/prompt/soft%20knitted%20wool%20scarf%2C%20pastel%20mint%20green%2C%20draped%20over%20a%20wooden%20chair%2C%20cozy%20atmosphere?width=600&height=450&seed=craft3` },
                { id: 4, title: "Floppy Ear Headbands", category: "Accessory", description: "Fun and floppy accessory, perfect for costume or daily whimsy.", color: "bg-yellow-100 text-yellow-700", imageUrl: `https://image.pollinations.ai/prompt/cute%20crochet%20bunny%20ear%20headband%2C%20worn%20by%20a%20child%20from%20behind%2C%20playing%20in%20a%20garden%2C%20soft%20sunlight?width=600&height=450&seed=craft4` },
                { id: 5, title: "Floral Hoop Art", category: "Embroidery", description: "Delicate stitched wall art with detailed floral and bunny motifs.", color: "bg-blue-100 text-blue-700", imageUrl: `https://image.pollinations.ai/prompt/intricate%20floral%20embroidery%20hoop%20art%2C%20with%20small%20bunnies%20among%20flowers%2C%20pastel%20threads%2C%20close-up%20texture?width=600&height=450&seed=craft5` },
                { id: 6, title: "Beginner Crochet Kits", category: "DIY Kit", description: "Everything you need to make your first tiny plushie!", color: "bg-cyan-100 text-cyan-700", imageUrl: `https://image.pollinations.ai/prompt/DIY%20crochet%20kit%20for%20beginners%2C%20with%20pastel%20yarn%2C%20crochet%20hook%2C%20and%20instructions%2C%20flat%20lay%2C%20cozy%20setting?width=600&height=450&seed=craft6` },
            ];

            // --- Icon Injection Function ---
            const injectIcon = (templateId, targetId) => {
                const template = document.getElementById(templateId);
                const target = document.getElementById(targetId);
                if (template && target) {
                    target.prepend(template.content.cloneNode(true));
                }
            };
            
            // Inject all necessary icons
            injectIcon('logo-svg', 'header-logo-container');
            injectIcon('rabbit-icon-svg', 'hero-rabbit-icon-container');
            injectIcon('heart-icon-svg', 'about-heart-icon-container');
            
            // Inject Instagram icons (must remove existing text first)
            const instagramHeaderLink = document.getElementById('instagram-link-header');
            if (instagramHeaderLink) {
                 instagramHeaderLink.prepend(document.getElementById('instagram-icon-svg').content.cloneNode(true));
            }
            const instagramFooterLink = document.getElementById('instagram-link-footer');
            if (instagramFooterLink) {
                 instagramFooterLink.prepend(document.getElementById('instagram-icon-svg').content.cloneNode(true));
            }


            // --- Gallery Rendering Function ---
            const galleryContainer = document.getElementById('gallery-container');

            CRAFT_ITEMS.forEach(item => {
                const card = document.createElement('div');
                card.className = "bg-white rounded-2xl shadow-xl overflow-hidden cursor-pointer transform hover:scale-[1.03] transition duration-300 ring-4 ring-transparent hover:ring-pink-300";

                card.innerHTML = `
                    <img
                        src="${item.imageUrl}"
                        alt="${item.title}"
                        class="w-full h-56 object-cover object-center"
                        onerror="this.onerror=null; this.src='https://placehold.co/600x450/cccccc/333333?text=Image+Not+Found'"
                    />
                    <div class="p-6">
                        <span class="inline-block mb-3 px-4 py-1 text-xs font-semibold ${item.color} rounded-full">
                            ${item.category}
                        </span>
                        <h3 class="text-2xl font-semibold text-pink-700 mb-2">${item.title}</h3>
                        <p class="text-gray-600 text-sm">${item.description}</p>
                    </div>
                `;
                galleryContainer.appendChild(card);
            });
        });
    </script>
</body>
</html>

    
