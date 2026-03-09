# My-fitness-GYM
Want a link for the website for the clients 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Fitness Center | Professional Gym Gadag</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- EmailJS SDK Integration -->
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0a0a0a;
            color: #ffffff;
            scroll-behavior: smooth;
            overflow-x: hidden;
        }
        .neon-red { color: #ff3131; }
        .bg-neon-red { background-color: #ff3131; }
        .border-neon-red { border-color: #ff3131; }
        
        .hover-glow:hover {
            box-shadow: 0 0 25px rgba(255, 49, 49, 0.5);
            transform: translateY(-3px);
        }
        
        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .sticky-nav {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .scrolled {
            background: rgba(10, 10, 10, 0.98);
            padding: 12px 0;
            border-bottom: 2px solid #ff3131;
        }

        .hidden-view {
            display: none;
            opacity: 0;
            transform: scale(0.95);
        }

        /* Loader Animation */
        .loader {
            border: 3px solid rgba(255, 255, 255, 0.2);
            border-top: 3px solid #ffffff;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            animation: spin 0.8s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        input, select, textarea {
            background: rgba(255, 255, 255, 0.05) !important;
            border: 1px solid rgba(255, 255, 255, 0.1) !important;
            color: white !important;
            transition: border-color 0.3s ease;
        }
        input:focus, select:focus {
            border-color: #ff3131 !important;
            outline: none;
            box-shadow: 0 0 10px rgba(255, 49, 49, 0.2);
        }

        .fade-in {
            animation: fadeIn 0.8s ease-out forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Markdown Styling for AI Response */
        .ai-content h3 { font-weight: 800; color: #ff3131; margin-top: 1rem; text-transform: uppercase; font-size: 0.9rem; }
        .ai-content p { margin-bottom: 0.5rem; font-size: 0.9rem; color: #ccc; }
        .ai-content ul { list-style: inside disc; margin-bottom: 1rem; color: #ccc; font-size: 0.85rem; }

        /* BMI Calculator Specifics */
        .bmi-indicator {
            height: 8px;
            border-radius: 4px;
            background: #333;
            position: relative;
            overflow: hidden;
        }
        .bmi-progress {
            height: 100%;
            width: 0%;
            transition: width 0.5s ease, background-color 0.5s ease;
        }
    </style>
</head>
<body>

    <!-- Top Notification -->
    <div class="bg-neon-red text-white py-2 px-4 text-center text-xs font-black uppercase tracking-[0.2em]">
        ⚡ Flash Sale: Join today and get a free personal training session! ⚡
    </div>

    <!-- Navigation -->
    <nav class="sticky-nav px-6 py-5 flex items-center justify-between" id="navbar">
        <div class="text-2xl font-extrabold tracking-tighter flex items-center cursor-pointer" onclick="window.location.reload()">
            <span class="text-white">MY</span>
            <span class="bg-neon-red text-black px-2 ml-1">FITNESS</span>
        </div>
        <div class="hidden md:flex space-x-8 font-bold uppercase text-xs tracking-widest">
            <a href="#home" class="hover:text-neon-red transition">Home</a>
            <a href="#services" class="hover:text-neon-red transition">Services</a>
            <a href="#pricing" class="hover:text-neon-red transition">Plans</a>
            <a href="#contact" class="hover:text-neon-red transition">Support</a>
        </div>
        <div class="flex items-center gap-4">
            <button onclick="document.getElementById('pricing').scrollIntoView()" class="bg-neon-red text-white px-5 py-2 rounded font-black uppercase text-[10px] hover:bg-white hover:text-black transition">Join</button>
        </div>
    </nav>

    <!-- Main Content Wrapper -->
    <main id="main-content">
        <!-- Hero Section -->
        <section id="home" class="relative min-h-screen flex items-center justify-center pt-20">
            <div class="absolute inset-0 z-0">
                <img src="https://images.unsplash.com/photo-1540497077202-7c8a3999166f?q=80&w=2070&auto=format&fit=crop" class="w-full h-full object-cover opacity-40 grayscale" alt="Gym Interior">
                <div class="absolute inset-0 bg-gradient-to-b from-black via-transparent to-black"></div>
            </div>
            <div class="relative z-10 text-center px-6 max-w-4xl fade-in">
                <h1 class="text-6xl md:text-9xl font-black mb-6 uppercase tracking-tighter leading-none">
                    NO <span class="neon-red">EXCUSES</span><br>JUST RESULTS.
                </h1>
                <p class="text-lg md:text-xl text-gray-400 mb-10 max-w-2xl mx-auto font-medium">
                    The most advanced fitness community in Gadag. Expert trainers, premium equipment, and results-driven programs.
                </p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button onclick="document.getElementById('pricing').scrollIntoView()" class="bg-neon-red text-white px-12 py-5 rounded-sm font-black uppercase text-sm hover-glow transition-all">Start Training</button>
                    <button onclick="document.getElementById('services').scrollIntoView()" class="bg-transparent border-2 border-white text-white px-12 py-5 rounded-sm font-black uppercase text-sm hover:bg-white hover:text-black transition-all">Explore Programs</button>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="services" class="py-24 px-6 bg-[#050505]">
            <div id="services-grid-container">
                <div class="max-w-7xl mx-auto text-center mb-16">
                    <p class="text-neon-red font-bold uppercase tracking-[0.3em] text-xs mb-4">Elite Programs</p>
                    <h2 class="text-5xl font-black uppercase tracking-tighter">Our Expertise</h2>
                </div>
                
                <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div class="glass p-8 rounded-lg group hover:border-neon-red transition-all">
                        <div class="w-full h-40 overflow-hidden mb-6 rounded">
                            <img src="https://images.unsplash.com/photo-1581009146145-b5ef03a7403f?q=80&w=2070&auto=format&fit=crop" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" alt="Weight Training">
                        </div>
                        <h4 class="text-xl font-black uppercase mb-3">Weight Training</h4>
                        <p class="text-gray-400 text-sm mb-6 leading-relaxed">Strength focus using elite Olympic-standard equipment.</p>
                        <button onclick="openService('weight-training')" class="text-xs font-black uppercase border-b-2 border-neon-red pb-1 hover:text-neon-red transition">Learn More</button>
                    </div>

                    <div class="glass p-8 rounded-lg group hover:border-neon-red transition-all">
                        <div class="w-full h-40 overflow-hidden mb-6 rounded">
                            <img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?q=80&w=2070&auto=format&fit=crop" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" alt="Fat Loss">
                        </div>
                        <h4 class="text-xl font-black uppercase mb-3">Fat Loss</h4>
                        <p class="text-gray-400 text-sm mb-6 leading-relaxed">HIIT conditioning designed to shred stubborn fat.</p>
                        <button onclick="openService('fat-loss')" class="text-xs font-black uppercase border-b-2 border-neon-red pb-1 hover:text-neon-red transition">Learn More</button>
                    </div>

                    <div class="glass p-8 rounded-lg group hover:border-neon-red transition-all">
                        <div class="w-full h-40 overflow-hidden mb-6 rounded">
                            <img src="https://images.unsplash.com/photo-1571019614242-c5c5dee9f50b?q=80&w=2070&auto=format&fit=crop" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" alt="Personal Training">
                        </div>
                        <h4 class="text-xl font-black uppercase mb-3">Personal Training</h4>
                        <p class="text-gray-400 text-sm mb-6 leading-relaxed">Dedicated 1-on-1 coaching for results-driven performance.</p>
                        <button onclick="openService('personal-training')" class="text-xs font-black uppercase border-b-2 border-neon-red pb-1 hover:text-neon-red transition">Learn More</button>
                    </div>

                    <div class="glass p-8 rounded-lg group hover:border-neon-red transition-all">
                        <div class="w-full h-40 overflow-hidden mb-6 rounded">
                            <img src="https://images.unsplash.com/photo-1490645935967-10de6ba17061?q=80&w=2070&auto=format&fit=crop" class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition duration-500" alt="Diet Plan">
                        </div>
                        <h4 class="text-xl font-black uppercase mb-3">Diet Guidance</h4>
                        <p class="text-gray-400 text-sm mb-6 leading-relaxed">Personalized macro-tracking and sustainable meal plans.</p>
                        <button onclick="openService('diet-guidance')" class="text-xs font-black uppercase border-b-2 border-neon-red pb-1 hover:text-neon-red transition">Learn More</button>
                    </div>
                </div>

                <!-- BMI Calculator Tool Integrated into Services -->
                <div class="max-w-4xl mx-auto mt-24 glass p-10 rounded-2xl border-l-4 border-l-neon-red">
                    <div class="flex flex-col md:flex-row gap-12">
                        <div class="md:w-1/2">
                            <p class="text-neon-red font-bold uppercase tracking-widest text-[10px] mb-2">Check Your Health</p>
                            <h3 class="text-3xl font-black uppercase mb-6">BMI Calculator</h3>
                            <div class="space-y-4">
                                <div>
                                    <label class="text-[10px] font-bold uppercase text-gray-500">Weight (kg)</label>
                                    <input type="number" id="bmi-weight" placeholder="e.g. 70" class="w-full p-4 rounded mt-1">
                                </div>
                                <div>
                                    <label class="text-[10px] font-bold uppercase text-gray-500">Height (cm)</label>
                                    <input type="number" id="bmi-height" placeholder="e.g. 175" class="w-full p-4 rounded mt-1">
                                </div>
                                <button onclick="calculateBMI()" class="w-full py-4 bg-neon-red text-white font-black uppercase text-xs hover:bg-white hover:text-black transition">Calculate Now</button>
                            </div>
                        </div>
                        <div class="md:w-1/2 flex flex-col justify-center text-center bg-black/40 p-8 rounded-xl">
                            <div id="bmi-result-container" class="opacity-30">
                                <p class="text-gray-500 text-[10px] font-bold uppercase mb-1">Your BMI Score</p>
                                <h2 id="bmi-score" class="text-6xl font-black mb-2">0.0</h2>
                                <p id="bmi-status" class="text-neon-red font-black uppercase tracking-widest text-sm mb-6">Enter Details</p>
                                
                                <div class="bmi-indicator mb-4">
                                    <div id="bmi-bar" class="bmi-progress"></div>
                                </div>
                                
                                <p id="bmi-desc" class="text-gray-400 text-xs leading-relaxed">BMI is a measure of body fat based on height and weight that applies to adult men and women.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="service-detail-view" class="hidden-view max-w-6xl mx-auto py-12">
                <button onclick="closeViews()" class="flex items-center gap-2 text-neon-red font-black uppercase text-xs mb-10 hover:text-white transition">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M10 19l-7-7m0 0l7-7m-7 7h18" stroke-width="2"/></svg>
                    Back to Services
                </button>
                <div id="detail-content-target"></div>
            </div>
        </section>

        <!-- Pricing Section -->
        <section id="pricing" class="py-24 px-6 bg-black">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-16">
                    <p class="text-neon-red font-bold uppercase tracking-[0.3em] text-xs mb-4">Pricing Plans</p>
                    <h2 class="text-5xl font-black uppercase tracking-tighter">Join the Tribe</h2>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="glass p-12 rounded-xl flex flex-col hover:border-white/20 transition-all">
                        <h3 class="text-xl font-black mb-2 uppercase">Basic</h3>
                        <div class="flex items-baseline mb-8">
                            <span class="text-4xl font-black">₹999</span>
                            <span class="text-gray-500 text-sm ml-2">/mo</span>
                        </div>
                        <ul class="space-y-4 mb-10 flex-grow text-gray-400 text-sm">
                            <li>✅ Unlimited Gym Access</li>
                            <li>✅ Locker Room Usage</li>
                            <li>✅ General Guidance</li>
                        </ul>
                        <button onclick="openSignup('Basic', '999')" class="w-full py-4 border-2 border-white rounded font-black uppercase text-xs hover:bg-white hover:text-black transition">Get Started</button>
                    </div>

                    <div class="bg-neon-red p-12 rounded-xl flex flex-col transform md:scale-105 shadow-2xl relative">
                        <div class="absolute -top-4 left-1/2 -translate-x-1/2 bg-white text-black px-4 py-1 rounded-full text-[10px] font-black uppercase">Most Popular</div>
                        <h3 class="text-xl font-black mb-2 uppercase">Standard</h3>
                        <div class="flex items-baseline mb-8">
                            <span class="text-4xl font-black text-white">₹1,999</span>
                            <span class="text-white/70 text-sm ml-2">/mo</span>
                        </div>
                        <ul class="space-y-4 mb-10 flex-grow text-white font-medium text-sm">
                            <li>✅ Everything in Basic</li>
                            <li>✅ Customized Diet Plan</li>
                            <li>✅ Group Fitness Classes</li>
                        </ul>
                        <button onclick="openSignup('Standard', '1999')" class="w-full py-4 bg-black text-white rounded font-black uppercase text-xs hover:bg-white hover:text-black transition">Join Now</button>
                    </div>

                    <div class="glass p-12 rounded-xl flex flex-col hover:border-white/20 transition-all">
                        <h3 class="text-xl font-black mb-2 uppercase">Premium</h3>
                        <div class="flex items-baseline mb-8">
                            <span class="text-4xl font-black">₹4,999</span>
                            <span class="text-gray-500 text-sm ml-2">/mo</span>
                        </div>
                        <ul class="space-y-4 mb-10 flex-grow text-gray-400 text-sm">
                            <li>✅ Everything in Standard</li>
                            <li>✅ 2 PT Sessions / Week</li>
                            <li>✅ Recovery Spa Access</li>
                        </ul>
                        <button onclick="openSignup('Premium', '4999')" class="w-full py-4 border-2 border-white rounded font-black uppercase text-xs hover:bg-white hover:text-black transition">Go Elite</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Support Section -->
        <section id="contact" class="py-24 px-6 bg-[#050505]">
            <div class="max-w-7xl mx-auto grid md:grid-cols-2 gap-16 items-center">
                <div class="rounded-xl overflow-hidden h-[400px] border border-white/10 grayscale hover:grayscale-0 transition duration-700">
                    <img src="https://images.unsplash.com/photo-1574680096145-d05b474e2155?q=80&w=2069&auto=format&fit=crop" class="w-full h-full object-cover" alt="Gym Motivation">
                </div>
                <div>
                    <h3 class="text-4xl font-black uppercase mb-8">Visit Us Today</h3>
                    <div class="space-y-6 text-gray-400">
                        <div class="flex gap-4">
                            <span class="text-neon-red font-bold">📍</span>
                            <p>Main Road, Gadag, Karnataka - 582101</p>
                        </div>
                        <div class="flex gap-4">
                            <span class="text-neon-red font-bold">⏰</span>
                            <p>Mon - Sat: 5:00 AM - 10:00 PM<br>Sun: 7:00 AM - 12:00 PM</p>
                        </div>
                        <div class="flex gap-4">
                            <span class="text-neon-red font-bold">📞</span>
                            <p>+91 99016 11123</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Fullscreen Signup Interface -->
    <section id="signup-view" class="hidden-view fixed inset-0 z-[2000] bg-black overflow-y-auto px-6 py-12">
        <div class="max-w-3xl mx-auto">
            <div class="flex justify-between items-center mb-12">
                <button onclick="closeViews()" class="text-neon-red font-black uppercase text-xs flex items-center gap-2 hover:text-white transition">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M10 19l-7-7m0 0l7-7m-7 7h18" stroke-width="2"/></svg>
                    Back to Plans
                </button>
                <div class="text-xl font-black tracking-tighter">MY <span class="bg-neon-red text-black px-1">FITNESS</span></div>
            </div>

            <div class="text-center mb-12">
                <h2 class="text-4xl font-black uppercase mb-2">Join My Fitness Gym</h2>
                <p class="text-gray-500 font-medium">Start your transformation today</p>
            </div>

            <div class="glass p-6 rounded-lg mb-12 flex justify-between items-center border-l-4 border-l-neon-red">
                <div>
                    <p class="text-[10px] font-black uppercase text-gray-500 mb-1">Selected Plan</p>
                    <h3 id="display-plan-name" class="text-2xl font-black uppercase">Standard</h3>
                </div>
                <div class="text-right">
                    <p class="text-[10px] font-black uppercase text-gray-500 mb-1">Monthly Cost</p>
                    <h3 id="display-plan-price" class="text-2xl font-black text-neon-red">₹1,999</h3>
                </div>
            </div>

            <form id="membershipForm" class="space-y-6">
                <!-- Hidden inputs for mapping to template -->
                <input type="hidden" name="plan" id="form-plan-hidden">
                <input type="hidden" name="price" id="form-price-hidden">

                <div class="grid md:grid-cols-2 gap-6">
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Full Name</label>
                        <input type="text" name="name" placeholder="Enter Name" class="w-full p-4 rounded" required>
                    </div>
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Phone Number</label>
                        <input type="tel" name="phone" placeholder="99016XXXXX" class="w-full p-4 rounded" required>
                    </div>
                </div>
                
                <div class="grid md:grid-cols-2 gap-6">
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Email Address</label>
                        <input type="email" name="email" placeholder="example@email.com" class="w-full p-4 rounded" required>
                    </div>
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Age</label>
                        <input type="number" name="age" id="form-age" placeholder="24" min="12" class="w-full p-4 rounded" required>
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-6">
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Fitness Goal</label>
                        <select name="goal" id="form-goal" class="w-full p-4 rounded" required>
                            <option value="" disabled selected>Select Fitness Goal</option>
                            <option value="Weight Loss">Weight Loss</option>
                            <option value="Muscle Gain">Muscle Gain</option>
                            <option value="General Fitness">General Fitness</option>
                        </select>
                    </div>
                    <div class="space-y-1">
                        <label class="text-[10px] font-bold uppercase text-gray-500">Preferred Time Slot</label>
                        <select name="time" class="w-full p-4 rounded" required>
                            <option value="" disabled selected>Select Preferred Time</option>
                            <option value="Morning (5-10 AM)">Morning (5-10 AM)</option>
                            <option value="Afternoon (12-4 PM)">Afternoon (12-4 PM)</option>
                            <option value="Evening (5-10 PM)">Evening (5-10 PM)</option>
                        </select>
                    </div>
                </div>
                
                <!-- Gemini AI Feature -->
                <div id="ai-suggestion-box" class="hidden glass p-6 rounded-lg border-l-4 border-l-white/20 mt-4">
                    <div class="flex items-center gap-2 mb-4">
                        <span class="text-lg">✨</span>
                        <h4 class="text-xs font-black uppercase tracking-widest text-white">Your Personal AI Strategy</h4>
                    </div>
                    <div id="ai-content-area" class="ai-content">
                        <!-- Content injected by JS -->
                    </div>
                </div>

                <div class="grid md:grid-cols-2 gap-4">
                    <button type="button" id="ai-btn" onclick="generateAISuggestion()" class="w-full py-4 bg-transparent border-2 border-white/20 text-white font-black uppercase text-xs hover:border-white transition flex items-center justify-center gap-2">
                        ✨ Generate AI Workout Plan
                    </button>
                    <button type="submit" id="submit-btn" class="w-full py-5 bg-neon-red text-white font-black uppercase text-sm hover-glow transition-all flex items-center justify-center gap-3">
                        Confirm Membership
                    </button>
                </div>

                <div class="pt-8 border-t border-white/10">
                    <h4 class="text-xs font-black uppercase tracking-widest mb-6">Select Payment Method</h4>
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                        <label class="cursor-pointer group">
                            <input type="radio" name="payment" value="UPI/GPay" class="hidden peer" checked>
                            <div class="p-4 border border-white/10 rounded text-center peer-checked:border-neon-red peer-checked:bg-neon-red/10 transition">
                                <p class="text-[10px] font-black uppercase">UPI / GPay</p>
                            </div>
                        </label>
                        <label class="cursor-pointer group">
                            <input type="radio" name="payment" value="Card" class="hidden peer">
                            <div class="p-4 border border-white/10 rounded text-center peer-checked:border-neon-red peer-checked:bg-neon-red/10 transition">
                                <p class="text-[10px] font-black uppercase">Card</p>
                            </div>
                        </label>
                        <label class="cursor-pointer group">
                            <input type="radio" name="payment" value="Cash" class="hidden peer">
                            <div class="p-4 border border-white/10 rounded text-center peer-checked:border-neon-red peer-checked:bg-neon-red/10 transition">
                                <p class="text-[10px] font-black uppercase">Cash</p>
                            </div>
                        </label>
                    </div>
                </div>
            </form>
        </div>
    </section>

    <!-- Success Modal -->
    <div id="success-modal" class="hidden fixed inset-0 z-[3000] flex items-center justify-center px-6">
        <div class="absolute inset-0 bg-black/90 backdrop-blur-sm"></div>
        <div class="relative glass max-w-md w-full p-10 rounded-2xl text-center fade-in">
            <div class="w-20 h-20 bg-neon-red text-white flex items-center justify-center rounded-full mx-auto mb-6">
                <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path d="M5 13l4 4L19 7" stroke-width="3"/></svg>
            </div>
            <h3 class="text-3xl font-black uppercase mb-4">You're In!</h3>
            <p class="text-gray-400 mb-8 leading-relaxed">Thank you for joining My Fitness! Our team will contact you soon.</p>
            <button onclick="window.location.reload()" class="w-full py-4 bg-white text-black font-black uppercase text-xs hover:bg-neon-red hover:text-white transition">Back to Home</button>
        </div>
    </div>

    <footer class="py-12 px-6 border-t border-white/5 bg-black">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between items-center gap-8 text-center md:text-left">
            <div class="text-2xl font-black tracking-tighter">MY <span class="bg-neon-red text-black px-1">FITNESS</span></div>
            <p class="text-gray-500 text-[10px] font-bold uppercase tracking-widest">© 2024 My Fitness Gym Gadag. Built for Champions.</p>
        </div>
    </footer>

    <script>
        // --- Gemini & EmailJS Config ---
        const apiKey = ""; // Provided by environment
        const PUBLIC_KEY = "4QZsGFISkKZ2KIYJ-";
        const SERVICE_ID = "service_3p5jxvg";
        const TEMPLATE_ID = "template_vdn8qw9";

        emailjs.init(PUBLIC_KEY);

        // --- BMI Calculator Functionality ---
        function calculateBMI() {
            const weight = parseFloat(document.getElementById('bmi-weight').value);
            const height = parseFloat(document.getElementById('bmi-height').value) / 100; // convert to meters
            
            if (!weight || !height) {
                alert("Please enter valid weight and height.");
                return;
            }

            const bmi = (weight / (height * height)).toFixed(1);
            const scoreEl = document.getElementById('bmi-score');
            const statusEl = document.getElementById('bmi-status');
            const descEl = document.getElementById('bmi-desc');
            const barEl = document.getElementById('bmi-bar');
            const container = document.getElementById('bmi-result-container');

            container.style.opacity = "1";
            scoreEl.innerText = bmi;

            let status = "";
            let color = "#ff3131";
            let width = 0;
            let advice = "";

            if (bmi < 18.5) {
                status = "Underweight";
                color = "#3b82f6"; // Blue
                width = 25;
                advice = "Focus on nutrient-dense calorie surplus and strength training to build muscle mass.";
            } else if (bmi < 25) {
                status = "Normal Weight";
                color = "#22c55e"; // Green
                width = 50;
                advice = "Great job! Maintain your current routine and focus on functional fitness and longevity.";
            } else if (bmi < 30) {
                status = "Overweight";
                color = "#eab308"; // Yellow
                width = 75;
                advice = "Incorporate more HIIT sessions and monitor macro intake to reach your optimal weight zone.";
            } else {
                status = "Obese";
                color = "#ff3131"; // Red
                width = 100;
                advice = "Consistent low-impact cardio and a strict calorie deficit are key. Let's start slow and steady.";
            }

            statusEl.innerText = status;
            statusEl.style.color = color;
            barEl.style.backgroundColor = color;
            barEl.style.width = width + "%";
            descEl.innerText = advice;
        }

        // --- Gemini AI Functionality ---
        async function generateAISuggestion() {
            const age = document.getElementById('form-age').value;
            const goal = document.getElementById('form-goal').value;
            const plan = document.getElementById('form-plan-hidden').value;
            const btn = document.getElementById('ai-btn');
            const box = document.getElementById('ai-suggestion-box');
            const content = document.getElementById('ai-content-area');

            if (!age || !goal) {
                alert("Please select your Age and Fitness Goal first!");
                return;
            }

            btn.disabled = true;
            btn.innerHTML = `<div class="loader"></div> Thinking...`;
            box.classList.remove('hidden');
            content.innerHTML = `<p class="animate-pulse">Curating your high-performance routine...</p>`;

            const systemPrompt = "You are an elite fitness strategist for 'My Fitness Gym'. Provide a concise, highly professional 4-week workout outline and diet tip based on user profile. Use short headers (h3) and bullet points. Focus on intensity and results. Format with basic HTML tags like h3, p, ul, li.";
            const userQuery = `Create a plan for a ${age} year old aiming for ${goal} on a ${plan} gym membership.`;

            let retries = 0;
            const callGemini = async () => {
                try {
                    const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify({
                            contents: [{ parts: [{ text: userQuery }] }],
                            systemInstruction: { parts: [{ text: systemPrompt }] }
                        })
                    });
                    
                    if (!response.ok) throw new Error('API Error');
                    
                    const data = await response.json();
                    const aiText = data.candidates?.[0]?.content?.parts?.[0]?.text;
                    
                    content.innerHTML = aiText;
                    btn.innerHTML = `✨ Regenerate Strategy`;
                    btn.disabled = false;
                } catch (error) {
                    if (retries < 5) {
                        retries++;
                        setTimeout(callGemini, Math.pow(2, retries) * 1000);
                    } else {
                        content.innerHTML = "<p>Our AI coach is currently training. Please try again in a moment.</p>";
                        btn.disabled = false;
                        btn.innerHTML = `✨ Try Again`;
                    }
                }
            };

            await callGemini();
        }

        const serviceContent = {
            'weight-training': {
                title: 'Weight Training',
                desc: 'Harness the power of iron. Our weight training zone features premium Olympic bars and isolation machines.',
                img: 'https://images.unsplash.com/photo-1534438327276-14e5300c3a48?q=80&w=2070'
            },
            'fat-loss': {
                title: 'Fat Loss',
                desc: 'Torching calories made simple. Our HIIT and cardio circuits are designed for maximum metabolic burn.',
                img: 'https://images.unsplash.com/photo-1549476464-37392f717541?q=80&w=2070'
            },
            'personal-training': {
                title: '1-on-1 Training',
                desc: 'Tailored coaching for your unique body type. Smash your plateaus with expert biomechanical oversight.',
                img: 'https://images.unsplash.com/photo-1594381898411-846e7d193883?q=80&w=2070'
            },
            'diet-guidance': {
                title: 'Diet Guidance',
                desc: 'Nutrition is 70% of the game. Get science-based macro breakdowns and meal plans that actually work.',
                img: 'https://images.unsplash.com/photo-1490645935967-10de6ba17061?q=80&w=2070'
            }
        };

        window.onscroll = () => {
            const nav = document.getElementById('navbar');
            if (window.scrollY > 50) nav.classList.add('scrolled');
            else nav.classList.remove('scrolled');
        };

        function openService(id) {
            const data = serviceContent[id];
            const target = document.getElementById('detail-content-target');
            target.innerHTML = `
                <div class="grid md:grid-cols-2 gap-16 fade-in">
                    <img src="${data.img}" class="w-full h-96 object-cover rounded-xl shadow-2xl grayscale hover:grayscale-0 transition duration-1000" />
                    <div>
                        <h2 class="text-5xl font-black uppercase mb-6">${data.title}</h2>
                        <p class="text-gray-400 text-lg mb-10 leading-relaxed">${data.desc}</p>
                        <button onclick="document.getElementById('pricing').scrollIntoView(); closeViews();" class="bg-neon-red text-white px-8 py-4 font-black uppercase text-xs hover-glow transition">Start This Program</button>
                    </div>
                </div>
            `;
            document.getElementById('services-grid-container').classList.add('hidden-view');
            document.getElementById('service-detail-view').classList.remove('hidden-view');
        }

        function openSignup(name, price) {
            document.getElementById('display-plan-name').innerText = name;
            document.getElementById('display-plan-price').innerText = `₹${price}`;
            
            // Populate hidden inputs for the email template
            document.getElementById('form-plan-hidden').value = name;
            document.getElementById('form-price-hidden').value = `₹${price}`;

            document.getElementById('main-content').classList.add('hidden-view');
            document.getElementById('navbar').classList.add('hidden');
            document.getElementById('signup-view').classList.remove('hidden-view');
            window.scrollTo(0,0);
        }

        function closeViews() {
            document.getElementById('services-grid-container').classList.remove('hidden-view');
            document.getElementById('service-detail-view').classList.add('hidden-view');
            document.getElementById('main-content').classList.remove('hidden-view');
            document.getElementById('navbar').classList.remove('hidden');
            document.getElementById('signup-view').classList.add('hidden-view');
        }

        // --- Membership Form Logic with EmailJS ---
        document.getElementById('membershipForm').addEventListener('submit', function(event) {
            event.preventDefault();

            const form = event.target;
            const btn = document.getElementById('submit-btn');
            const originalBtnText = "Confirm Membership";

            // Basic Validation
            if (!form.checkValidity()) return;

            // Show Loading Animation
            btn.innerHTML = `<div class="loader"></div> Processing...`;
            btn.disabled = true;

            // Send via EmailJS sendForm method
            emailjs.sendForm(SERVICE_ID, TEMPLATE_ID, this)
                .then(function() {
                    console.log('SUCCESS!');
                    
                    // Show Success Modal
                    document.getElementById('success-modal').classList.remove('hidden');
                    
                    // Clear the form
                    form.reset();
                    btn.innerHTML = originalBtnText;
                    btn.disabled = false;

                }, function(error) {
                    console.error('FAILED...', error);
                    alert("Submission failed. Please try again later.");
                    btn.innerHTML = originalBtnText;
                    btn.disabled = false;
                });
        });
    </script>
</body>
</html>
