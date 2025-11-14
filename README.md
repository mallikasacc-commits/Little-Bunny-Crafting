# Little-Bunny-Crafting
Art and Craft

import React from 'react';

// --- Icon Components (Simulated Lucide Icons for Single-File React) ---
const InstagramIcon = (props) => (
  <svg {...props} xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
    <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
    <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
  </svg>
);

const HeartIcon = (props) => (
    <svg {...props} xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
        <path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/>
    </svg>
);

const RabbitIcon = (props) => (
    <svg {...props} xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
        <path d="M18.87 9.17c-1.07-1.1-2.45-2-4.43-2.61a1.27 1.27 0 0 0-1.08.31c-.5.42-1.19.42-1.69 0a1.27 1.27 0 0 0-1.08-.31c-1.98.61-3.36 1.51-4.43 2.61C4.3 10.3 3 12.2 3 14c0 1.8 1.3 3.7 3.17 4.83l.53.33c.9.56 2.0 .94 3.13 1.09a7.35 7.35 0 0 0 4.34 0c1.13-.15 2.23-.53 3.13-1.09l.53-.33C19.7 17.7 21 15.8 21 14c0-1.8-1.3-3.7-3.13-4.83Z"/>
        <path d="M16 9c.14-.62.27-1.3.4-2l.5-3.5"/>
        <path d="M8 9c-.14-.62-.27-1.3-.4-2l-.5-3.5"/>
    </svg>
);

// Logo is now an Inline SVG for guaranteed loading
const LogoIcon = (props) => (
  <svg {...props} xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round">
    {/* Bunny Body - Filled with soft pink */}
    <path className="fill-pink-200 stroke-pink-700" d="M18.87 9.17c-1.07-1.1-2.45-2-4.43-2.61a1.27 1.27 0 0 0-1.08.31c-.5.42-1.19.42-1.69 0a1.27 1.27 0 0 0-1.08-.31c-1.98.61-3.36 1.51-4.43 2.61C4.3 10.3 3 12.2 3 14c0 1.8 1.3 3.7 3.17 4.83l.53.33c.9.56 2.0 .94 3.13 1.09a7.35 7.35 0 0 0 4.34 0c1.13-.15 2.23-.53 3.13-1.09l.53-.33C19.7 17.7 21 15.8 21 14c0-1.8-1.3-3.7-3.13-4.83Z"/>
    {/* Left Ear */}
    <path className="stroke-pink-700" d="M16 9c.14-.62.27-1.3.4-2l.5-3.5"/>
    {/* Right Ear */}
    <path className="stroke-pink-700" d="M8 9c-.14-.62-.27-1.3-.4-2l-.5-3.5"/>
    {/* Small Heart detail for crafting/love */}
    <path className="fill-red-400 stroke-red-500" strokeWidth="0.5" d="M12 18l-1-1a3 3 0 0 1 4 0l-1 1z"/>
  </svg>
);

// --- Dummy Data for Gallery (Updated to use reliable placeholders) ---
const CRAFT_ITEMS = [
  { id: 1, title: "Amigurumi Bunny", category: "Crochet", description: "A soft, plush companion, handcrafted with premium yarn. Perfect for snuggling.", color: "bg-purple-100 text-purple-700", imageUrl: `https://placehold.co/600x450/FBEAFF/7E33C8?text=Crochet+Bunny` },
  { id: 2, title: "Custom Greeting Cards", category: "Papercraft", description: "Intricate, layered designs for birthdays and special occasions.", color: "bg-red-100 text-red-700", imageUrl: `https://placehold.co/600x450/FFEFFA/C8337E?text=Greeting+Card` },
  { id: 3, title: "Wool Knit Scarves", category: "Knitting", description: "Cozy hand-knitted scarf made from organic, hypoallergenic wool blend.", color: "bg-green-100 text-green-700", imageUrl: `https://placehold.co/600x450/E9FFF0/33C84B?text=Knit+Scarf` },
  { id: 4, title: "Floppy Ear Headbands", category: "Accessory", description: "Fun and floppy accessory, perfect for costume or daily whimsy.", color: "bg-yellow-100 text-yellow-700", imageUrl: `https://placehold.co/600x450/FFFBEA/C87E33?text=Bunny+Headband` },
  { id: 5, title: "Floral Hoop Art", category: "Embroidery", description: "Delicate stitched wall art with detailed floral and bunny motifs.", color: "bg-blue-100 text-blue-700", imageUrl: `https://placehold.co/600x450/EAFFFB/33C8C4?text=Embroidery+Art` },
  { id: 6, title: "Beginner Crochet Kits", category: "DIY Kit", description: "Everything you need to make your first tiny plushie!", color: "bg-cyan-100 text-cyan-700", imageUrl: `https://placehold.co/600x450/FFFEFA/7E3333?text=DIY+Kit` },
];

const INSTAGRAM_LINK = "https://www.instagram.com/little_bunny_crafting?igsh=d3J3eXE1cjd2OHBp";


// --- Component Definitions ---

const Header = () => (
    <header className="sticky top-0 z-10 bg-white shadow-lg">
        <div className="container mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#" className="flex items-center text-3xl font-pacifico text-pink-600 hover:text-pink-700 transition duration-300">
                {/* Logo is now an Inline SVG */}
                <LogoIcon className="h-10 w-10 mr-3 text-pink-700" />
                Little Bunny Crafting
            </a>
            <nav className="space-x-4">
                <a href="#about" className="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">About</a>
                <a href="#gallery" className="text-gray-600 hover:text-pink-600 transition duration-300 hidden sm:inline">Gallery</a>
                <a href={INSTAGRAM_LINK} target="_blank" rel="noopener noreferrer" className="bg-pink-500 text-white px-4 py-2 rounded-full shadow-md hover:bg-pink-600 transition duration-300 text-sm flex items-center">
                    <InstagramIcon className="w-4 h-4 mr-2" /> Follow
                </a>
            </nav>
        </div>
    </header>
);

const Hero = () => (
    <section className="py-16 md:py-24 bg-pink-100/50 relative overflow-hidden">
        {/* Decorative background image - now using reliable placeholder */}
        <div className="absolute inset-0 z-0 opacity-20">
            <img
                src={`https://placehold.co/1920x1080/FFEAEA/FBC3C3?text=Crafting+Background+Texture`}
                alt="Soft crafting background"
                className="w-full h-full object-cover"
            />
        </div>
        <div className="container mx-auto px-4 text-center relative z-10">
            <div className="max-w-3xl mx-auto">
                <RabbitIcon className="w-16 h-16 mx-auto text-pink-600 mb-4 animate-bounce-slow" />
                <h1 className="text-5xl md:text-6xl font-extrabold text-pink-700 leading-tight mb-4 drop-shadow-md">
                    Handmade Happiness, One Stitch at a Time
                </h1>
                <p className="text-xl text-gray-700 mb-8 max-w-xl mx-auto drop-shadow-sm">
                    Welcome to our cozy corner of creativity. We specialize in adorable, custom-made crafts inspired by all things cute and fluffy!
                </p>
                <a href={INSTAGRAM_LINK} target="_blank" rel="noopener noreferrer" className="inline-block bg-pink-500 text-white text-xl font-semibold px-8 py-3 rounded-xl shadow-lg hover:bg-pink-600 transform hover:scale-105 transition duration-300 ease-in-out">
                    See Our Latest Posts on Instagram
                </a>
            </div>
        </div>
    </section>
);

const About = () => (
    <section id="about" className="py-16 md:py-20">
        <div className="container mx-auto px-4 max-w-5xl">
            <h2 className="text-4xl font-bold text-center text-pink-600 mb-10">Our Story & Mission</h2>
            <div className="flex flex-col md:flex-row items-center space-y-8 md:space-y-0 md:space-x-12 bg-white p-6 md:p-10 rounded-2xl shadow-xl">
                <div className="md:w-1/2">
                    <img
                        // Now using a reliable placeholder
                        src={`https://placehold.co/600x400/F5D0FE/9333EA?text=Whimsical+Crafting+Desk`}
                        alt="A whimsical crafting setup"
                        className="rounded-xl shadow-lg w-full h-auto object-cover"
                    />
                </div>
                <div className="md:w-1/2 text-lg text-gray-700 space-y-4">
                    <p>
                        **Little Bunny Crafting** started as a simple, heartfelt hobby. It quickly grew into a passion for creating personalized, heartwarming gifts. Every item is made with love and the utmost attention to detail.
                    </p>
                    <p>
                        We believe that a handmade gift carries a piece of the maker's heart. By focusing on sustainable materials and gentle designs, we aim to bring joy and a little bit of magic into your home.
                    </p>
                    <div className="flex items-center text-pink-600 font-semibold pt-2">
                        <HeartIcon className="w-6 h-6 mr-2 fill-pink-600/10" />
                        Handmade with Love, Always.
                    </div>
                </div>
            </div>
        </div>
    </section>
);

const Gallery = ({ items }) => (
    <section id="gallery" className="py-16 md:py-20 bg-pink-50">
        <div className="container mx-auto px-4">
            <h2 className="text-4xl font-bold text-center text-pink-600 mb-12">Latest Creations</h2>

            <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
                {items.map(item => (
                    <div
                        key={item.id}
                        className="bg-white rounded-2xl shadow-xl overflow-hidden cursor-pointer
                                   transform hover:scale-[1.03] transition duration-300 ring-4 ring-transparent hover:ring-pink-300"
                    >
                        <img
                            src={item.imageUrl}
                            alt={item.title}
                            className="w-full h-56 object-cover object-center"
                            onError={(e) => { e.target.onerror = null; e.target.src="https://placehold.co/600x450/cccccc/333333?text=Image+Not+Found" }}
                        />
                        <div className="p-6">
                            <span className={`inline-block mb-3 px-4 py-1 text-xs font-semibold ${item.color} rounded-full`}>
                                {item.category}
                            </span>
                            <h3 className="text-2xl font-semibold text-pink-700 mb-2">{item.title}</h3>
                            <p className="text-gray-600 text-sm">{item.description}</p>
                        </div>
                    </div>
                ))}
            </div>
        </div>
    </section>
);

const Footer = () => (
    <footer id="contact" className="bg-pink-700 text-white py-12">
        <div className="container mx-auto px-4 text-center">
            <h2 className="text-3xl font-bold mb-4">Connect with the Bunny!</h2>
            <p className="text-pink-200 mb-6">For custom orders or collaborations, join our crafting community.</p>

            <a href={INSTAGRAM_LINK} target="_blank" rel="noopener noreferrer" className="inline-flex items-center bg-pink-500 text-white font-semibold px-6 py-3 rounded-full shadow-xl hover:bg-pink-400 transition duration-300">
                <InstagramIcon className="w-6 h-6 mr-3" />
                @little_bunny_crafting
            </a>

            <div className="mt-8 pt-6 border-t border-pink-600">
                <p className="text-sm text-pink-300">&copy; 2024 Little Bunny Crafting. All Rights Reserved.</p>
            </div>
        </div>
    </footer>
);


// --- Main App Component ---
export default function App() {
  return (
    <div className="min-h-screen bg-pink-50 text-gray-800 antialiased">
      {/* Custom Fonts for a charming look */}
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Pacifico&display=swap');
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
      `}</style>
      <Header />
      <main>
        <Hero />
        <About />
        <Gallery items={CRAFT_ITEMS} />
      </main>
      <Footer />
    </div>
  );
}

