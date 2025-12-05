@@ -1,149 +1,182 @@
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UCM Scholarship Portal - Home/Search</title>
    <title>UCM Scholarship Finder</title>

    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

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
                        'ucm-dark': '#1a1a1a',
                        'bg-gray': '#f4f4f4',
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
            background-color: #f3f4f6;
        }
    </style>
</head>
<body class="text-gray-800 antialiased">

    <script>
        // Switch between Home and Results
        function switchView(viewId) {
            const views = ['view-home', 'view-results'];
            const navElements = {
                'view-home': document.getElementById('nav-home'),
                'view-results': document.getElementById('nav-results')
            };
    <header class="bg-ucm-red text-white shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="bg-white text-ucm-red rounded-full w-10 h-10 flex items-center justify-center font-bold text-xl">
                    UCM
                </div>
                <h1 class="text-2xl font-bold tracking-tight">Scholarship Finder</h1>
            </div>
            <div class="flex items-center gap-4">
                <button class="bg-ucm-gold text-ucm-red font-bold py-2 px-6 rounded shadow hover:bg-yellow-400 transition">
                    Sign In
                </button>
                <button class="text-white hover:text-gray-200">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-7 h-7">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M11.25 11.25l.041-.02a.75.75 0 011.063.852l-.708 2.836a.75.75 0 001.063.853l.041-.021M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9-3.75h.008v.008H12V8.25z" />
                    </svg>
                </button>
            </div>
        </div>
    </header>

            // Hide all views
            views.forEach(id => {
                document.getElementById(id).classList.add('hidden');
            });
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <div class="grid grid-cols-1 lg:grid-cols-4 gap-8">
            
            <aside class="lg:col-span-1">
                <div class="bg-white p-6 rounded-lg shadow-sm border border-gray-200 sticky top-4">
                    <h2 class="text-xl font-bold mb-6 text-gray-900 border-b pb-2">Filter Opportunities</h2>
                    
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Search by Keyword</label>
                        <input type="text" placeholder="e.g., Biology, Leadership" class="w-full border-gray-300 border rounded-md p-2 focus:ring-ucm-red focus:border-ucm-red shadow-sm text-sm">
                    </div>

            // Show selected view
            document.getElementById(viewId).classList.remove('hidden');
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Department Scope</label>
                        <select class="w-full border-gray-300 border rounded-md p-2 bg-white text-sm shadow-sm focus:border-ucm-red focus:ring-ucm-red">
                            <option>All Departments (54)</option>
                            <option>Business (12)</option>
                            <option>Arts (8)</option>
                        </select>
                    </div>

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
                    <div class="mb-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Award Type</label>
                        <div class="space-y-2">
                            <div class="flex items-center">
                                <input type="checkbox" checked class="h-4 w-4 text-ucm-red focus:ring-ucm-red border-gray-300 rounded">
                                <label class="ml-2 text-sm text-gray-600">Scholarship (40)</label>
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" class="h-4 w-4 text-ucm-red focus:ring-ucm-red border-gray-300 rounded">
                                <label class="ml-2 text-sm text-gray-600">Grant (8)</label>
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" class="h-4 w-4 text-ucm-red focus:ring-ucm-red border-gray-300 rounded">
                                <label class="ml-2 text-sm text-gray-600">Award/Prize (6)</label>
                            </div>
                            <div class="flex items-center">
                                <input type="checkbox" class="h-4 w-4 text-ucm-red focus:ring-ucm-red border-gray-300 rounded">
                                <label class="ml-2 text-sm text-gray-600">Pending Application (2)</label>
                            </div>
                        </div>
                    </div>

        function openModal() {
            document.getElementById('detail-modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('detail-modal').classList.add('hidden');
        }
                    <button class="w-full bg-ucm-red text-white font-bold py-2.5 rounded-md hover:bg-red-800 transition shadow-sm">
                        Apply Filters
                    </button>
                </div>
            </aside>

        // Initialize on load
        document.addEventListener('DOMContentLoaded', () => {
            switchView('view-home');
        });
    </script>
</head>
<body class="antialiased text-gray-800">
            <main class="lg:col-span-3 space-y-6">
                <div class="flex flex-col sm:flex-row justify-between items-center mb-4">
                    <h2 class="text-2xl font-bold text-gray-800">Opportunities for You <span class="text-gray-500 text-lg font-normal">(54 Total)</span></h2>
                    <div class="flex items-center gap-2 mt-2 sm:mt-0">
                        <label class="text-sm text-gray-600">Sort:</label>
                        <select class="border-gray-300 border rounded p-1 text-sm bg-white">
                            <option>Deadline (Earliest)</option>
                            <option>Award Amount</option>
                        </select>
                    </div>
                </div>

    <div id="template-container" class="w-full max-w-[1080px] bg-ucm-surface flex flex-col shadow-2xl rounded-xl overflow-hidden min-h-[80vh]">
        
        <div class="w-full h-10 bg-ucm-red text-white flex justify-between items-center px-6 text-sm opacity-90">
            <span>9:41</span>
            <div class="flex items-center space-x-2">
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>
                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M15.67 4H14V2h-4v2H8.33C7.6 4 7 4.6 7 5.33v15.33C7 21.4 7.6 22 8.33 22h7.33c.74 0 1.34-.6 1.34-1.33V5.33C17 4.6 16.4 4 15.67 4z"/></svg>
            </div>
        </div>
                <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6 hover:shadow-md transition">
                    <div class="flex justify-between items-start">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">A. Ralph Boxell Eagle Scout Scholarship</h3>
                        <button class="text-gray-400 hover:text-ucm-red">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M17.593 3.322c1.1.128 1.907 1.077 1.907 2.185V21L12 17.25 4.5 21V5.507c0-1.108.806-2.057 1.907-2.185a48.507 48.507 0 0111.186 0z" /></svg>
                        </button>
                    </div>
                    <p class="text-gray-600 mb-4 text-sm">Available through the UCM Alumni Foundation for active Eagle Scouts enrolled at UCM.</p>
                    
                    <div class="flex flex-wrap gap-3">
                        <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold">Amount: Varies</span>
                        <span class="bg-yellow-100 text-yellow-800 px-3 py-1 rounded-full text-xs font-bold">Deadline: Mar 15, 2026</span>
                        <span class="bg-red-50 text-red-800 px-3 py-1 rounded-full text-xs font-medium">General Application</span>
                    </div>
                </div>

        <header class="bg-ucm-red shadow-lg p-6 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="flex items-center space-x-4 cursor-pointer" onclick="switchView('view-home')">
                <div class="w-14 h-14 bg-white rounded-full flex items-center justify-center text-ucm-red font-extrabold text-2xl shadow-md">
                    UCM
                <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6 hover:shadow-md transition relative overflow-hidden">
                    <div class="absolute left-0 top-0 bottom-0 w-1 bg-ucm-red"></div>
                    
                    <div class="flex justify-between items-start">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Harmon College Business Graduate Scholarship</h3>
                        <button class="text-ucm-red">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path fill-rule="evenodd" d="M6.32 2.577a49.255 49.255 0 0111.36 0c1.497.174 2.57 1.46 2.57 2.93V21a.75.75 0 01-1.085.67L12 18.089l-7.165 3.583A.75.75 0 013.75 21V5.507c0-1.47 1.073-2.756 2.57-2.93z" clip-rule="evenodd" /></svg>
                        </button>
                    </div>
                    <p class="text-gray-600 mb-4 text-sm">Established to support outstanding graduate students within the Harmon College of Business & Professional Studies.</p>
                    
                    <div class="flex flex-wrap gap-3">
                        <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold">Amount: Full Ride</span>
                        <span class="bg-yellow-50 text-yellow-700 px-3 py-1 rounded-full text-xs font-bold border border-yellow-200">Status: PENDING REVIEW</span>
                        <span class="bg-blue-50 text-blue-700 px-3 py-1 rounded-full text-xs font-medium">Harmon College Specific</span>
                    </div>
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
                <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6 hover:shadow-md transition">
                    <div class="flex justify-between items-start">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Accountancy Scholarship Fund</h3>
                        <button class="text-gray-400 hover:text-ucm-red">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M17.593 3.322c1.1.128 1.907 1.077 1.907 2.185V21L12 17.25 4.5 21V5.507c0-1.108.806-2.057 1.907-2.185a48.507 48.507 0 0111.186 0z" /></svg>
                        </button>
                    </div>
                    <p class="text-gray-600 mb-4 text-sm">The Department of Accountancy Scholarship is available through the UCM Alumni Foundation.</p>
                    
                    <div class="flex flex-wrap gap-3">
                        <span class="bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold">Amount: $1,000</span>
                        <span class="bg-yellow-100 text-yellow-800 px-3 py-1 rounded-full text-xs font-bold">Deadline: Mar 15, 2026</span>
                        <span class="bg-red-50 text-red-800 px-3 py-1 rounded-full text-xs font-medium">Departmental</span>
                    </div>
                </div>

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
                <div class="flex justify-center mt-8 gap-2">
                    <button class="px-4 py-2 bg-white border border-gray-300 rounded text-sm text-gray-500 hover:bg-gray-50">Previous</button>
                    <button class="px-4 py-2 bg-ucm-red text-white border border-ucm-red rounded text-sm font-bold">1</button>
                    <button class="px-4 py-2 bg-white border border-gray-300 rounded text-sm text-gray-700 hover:bg-gray-50">2</button>
                    <button class="px-4 py-2 bg-white border border-gray-300 rounded text-sm text-gray-700 hover:bg-gray-50">3</button>
                    <button class="px-4 py-2 bg-white border border-gray-300 rounded text-sm text-gray-500 hover:bg-gray-50">Next</button>
                </div>
            </main>
        </div>
    </div>

            <div class="grid
</body>
</html>
