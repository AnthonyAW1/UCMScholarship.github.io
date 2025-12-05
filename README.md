<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UCM Scholarship Portal - Home/Search</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    
    <script src="https://cdn.tailwindcss.com"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'ucm-red': '#990000',
                        'ucm-gold': '#ffcc00',
                        'ucm-light': '#fefefe',
                        'ucm-surface': '#f9fafb',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #e5e7eb;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            padding-top: 20px;
            padding-bottom: 20px;
        }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: #c1c1c1;
            border-radius: 5px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #a8a8a8;
        }
    </style>

    <script>
        // Switch between Home and Results
        function switchView(viewId) {
            const views = ['view-home', 'view-results'];
            const navElements = {
                'view-home': document.getElementById('nav-home'),
                'view-results': document.getElementById('nav-results')
            };

            // Hide all views
            views.forEach(id => {
                document.getElementById(id).classList.add('hidden');
            });

            // Show selected view
            document.getElementById(viewId).classList.remove('hidden');

            // Update Buttons
            Object.keys(navElements).forEach(id => {
                const isSelected = id === viewId;
                const btn = navElements[id];
                
                if(isSelected) {
                    btn.classList.remove('bg-white', 'border-ucm-red');
                    btn.classList.add('bg-ucm-gold', 'border-transparent', 'font-extrabold');
                } else {
                    btn.classList.add('bg-white', 'border-ucm-red', 'font-semibold');
                    btn.classList.remove('bg-ucm-gold', 'border-transparent', 'font-extrabold');
                }
            });
        }

        function openModal() {
            document.getElementById('detail-modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('detail-modal').classList.add('hidden');
        }

        // Initialize on load
        document.addEventListener('DOMContentLoaded', () => {
            switchView('view-home');
        });
    </script>
</head>
<body class="antialiased text-gray-800">

    <div id="template-container" class="w-full max-w-[1080px] bg-ucm-surface flex flex-col shadow-2xl rounded-xl overflow-hidden min-h-[80vh]">
        
        <div class="w-full h-10 bg-ucm-red text-white flex justify-between items-center px-6 text-sm opacity-90">
            <span>9:41</span>
            <div class="flex items-center space-x-2">
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M15.67 4H14V2h-4v2H8.33C7.6 4 7 4.6 7 5.33v15.33C7 21.4 7.6 22 8.33 22h7.33c.74 0 1.34-.6 1.34-1.33V5.33C17 4.6 16.4 4 15.67 4z"/></svg>
            </div>
        </div>

        <header class="bg-ucm-red shadow-lg p-6 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="flex items-center space-x-4 cursor-pointer" onclick="switchView('view-home')">
                <div class="w-14 h-14 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-2xl shadow-md">
                    UCM
                </div>
                <h1 class="text-3xl font-bold text-white tracking-wide">
                    Scholarship Portal
                </h1>
            </div>

            <nav class="flex gap-4">
                <button id="nav-home" onclick="switchView('view-home')" class="bg-ucm-gold text-ucm-red font-extrabold py-2 px-6 rounded-xl shadow-md hover:opacity-90 transition">
                    Search
                </button>
                <button id="nav-results" onclick="switchView('view-results')" class="bg-white text-ucm-red font-semibold py-2 px-6 rounded-xl shadow-md hover:bg-gray-100 transition border-2 border-ucm-red">
                    My Decisions
                </button>
            </nav>
        </header>

        <main id="view-home" class="flex-grow p-6 overflow-y-auto">
            
            <section class="bg-white p-8 rounded-2xl shadow-md border-t-8 border-ucm-red mb-8">
                <h2 class="text-3xl font-extrabold text-gray-900 mb-3 flex items-center">
                    Find Your Funding
                </h2>
                <p class="text-lg text-gray-600 mb-6">
                    Welcome to the UCM Scholarship Portal! Complete the General Application to be matched with dozens of awards automatically.
                </p>
                <button class="bg-ucm-gold text-ucm-red font-extrabold py-3 px-8 text-lg rounded-xl shadow-lg hover:bg-opacity-80 transition">
                    Complete General Application &rarr;
                </button>
            </section>

            <div class="grid
