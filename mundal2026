<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mundial 2026 • App Oficial</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&amp;family=Space+Grotesk:wght@500;600&amp;display=swap');
        
        :root {
            --tw-color-primary: #00d4ff;
        }
        
        * {
            transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        
        .tail-container * {
            font-family: 'Inter', system_ui, sans-serif;
        }
        
        .logo-font {
            font-family: 'Space Grotesk', sans-serif;
        }

        .nav-link {
            position: relative;
        }
        
        .nav-link:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -2px;
            left: 0;
            background-color: #00d4ff;
        }
        
        .nav-link:hover:after,
        .nav-link.active:after {
            width: 100%;
        }
        
        .section {
            animation: fadeIn 0.4s ease forwards;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .card-hover {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .card-hover:hover {
            transform: translateY(-4px);
            box-shadow: 0 25px 50px -12px rgb(0 212 255 / 0.15);
        }
        
        .live-dot {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
        
        .modal {
            animation: modalPop 0.3s ease forwards;
        }
    </style>
</head>
<body class="tail-container bg-zinc-950 text-white min-h-screen pb-20">
    <!-- NAVBAR -->
    <nav class="bg-zinc-900 border-b border-zinc-800 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-6 py-5 flex items-center justify-between">
            <!-- Logo -->
            <div class="flex items-center gap-x-3">
                <div class="w-9 h-9 bg-gradient-to-br from-cyan-400 to-blue-500 rounded-2xl flex items-center justify-center text-2xl shadow-inner">
                    🏆
                </div>
                <h1 class="logo-font text-3xl tracking-[-1px]">Mundial 2026</h1>
                <span class="text-xs px-3 py-1 bg-cyan-400/10 text-cyan-400 rounded-3xl font-medium border border-cyan-400/30">ESTADOS UNIDOS • CANADÁ • MÉXICO</span>
            </div>

            <!-- Menú -->
            <div class="hidden md:flex items-center gap-x-8 text-sm font-medium">
                <a onclick="navigateTo('home')" class="nav-link cursor-pointer flex items-center gap-x-1 active" id="nav-home">
                    <i class="fa-solid fa-house"></i>
                    <span>Inicio</span>
                </a>
                <a onclick="navigateTo('matches')" class="nav-link cursor-pointer flex items-center gap-x-1" id="nav-matches">
                    <i class="fa-solid fa-calendar"></i>
                    <span>Partidos</span>
                </a>
                <a onclick="navigateTo('teams')" class="nav-link cursor-pointer flex items-center gap-x-1" id="nav-teams">
                    <i class="fa-solid fa-users"></i>
                    <span>Equipos</span>
                </a>
                <a onclick="navigateTo('standings')" class="nav-link cursor-pointer flex items-center gap-x-1" id="nav-standings">
                    <i class="fa-solid fa-table"></i>
                    <span>Clasificación</span>
                </a>
                <a onclick="navigateTo('stats')" class="nav-link cursor-pointer flex items-center gap-x-1" id="nav-stats">
                    <i class="fa-solid fa-chart-bar"></i>
                    <span>Estadísticas</span>
                </a>
                <a onclick="navigateTo('news')" class="nav-link cursor-pointer flex items-center gap-x-1" id="nav-news">
                    <i class="fa-solid fa-newspaper"></i>
                    <span>Noticias</span>
                </a>
            </div>

            <!-- Acciones derecha -->
            <div class="flex items-center gap-x-4">
                <!-- Selector de equipo favorito -->
                <div onclick="showFavoriteModal()" class="flex items-center gap-x-2 bg-zinc-800 hover:bg-zinc-700 px-4 h-10 rounded-3xl cursor-pointer border border-zinc-700">
                    <span class="text-xl" id="favorite-flag">🇲🇽</span>
                    <span class="text-sm font-medium" id="favorite-name">México</span>
                    <i class="fa-solid fa-chevron-down text-xs"></i>
                </div>

                <!-- Notificaciones -->
                <div onclick="fakeNotification()" class="relative cursor-pointer w-10 h-10 flex items-center justify-center rounded-2xl hover:bg-zinc-800">
                    <i class="fa-solid fa-bell text-xl"></i>
                    <span id="notification-badge" class="absolute top-2 right-2 text-[10px] bg-red-500 text-white w-4 h-4 flex items-center justify-center rounded-full">3</span>
                </div>

                <!-- Perfil -->
                <div class="flex items-center gap-x-3 cursor-pointer" onclick="showProfile()">
                    <div class="text-right">
                        <p class="text-sm font-medium">Sofía Rivera</p>
                        <p class="text-xs text-zinc-400">CDMX • Fanática 🇲🇽</p>
                    </div>
                    <div class="w-9 h-9 bg-gradient-to-br from-purple-400 to-pink-400 rounded-2xl flex items-center justify-center text-xl shadow-inner">👩‍💼</div>
                </div>

                <!-- Mobile menu -->
                <button onclick="toggleMobileMenu()" class="md:hidden w-10 h-10 flex items-center justify-center text-2xl">
                    <i class="fa-solid fa-bars" id="mobile-icon"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-zinc-900 border-t border-zinc-800 px-6 py-4">
            <div class="flex flex-col gap-y-4 text-sm font-medium">
                <a onclick="navigateTo('home');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">🏠 Inicio</a>
                <a onclick="navigateTo('matches');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">📅 Partidos</a>
                <a onclick="navigateTo('teams');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">👥 Equipos</a>
                <a onclick="navigateTo('standings');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">📊 Clasificación</a>
                <a onclick="navigateTo('stats');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">📈 Estadísticas</a>
                <a onclick="navigateTo('news');toggleMobileMenu()" class="flex items-center gap-x-3 py-2 px-4 hover:bg-zinc-800 rounded-2xl">📰 Noticias</a>
            </div>
        </div>
    </nav>

    <!-- CONTENIDO PRINCIPAL -->
    <main class="max-w-7xl mx-auto px-6 pt-8">
        
        <!-- SECCIÓN 1: INICIO (HOME) -->
        <div id="screen-home" class="section">
            <div class="rounded-3xl bg-gradient-to-br from-zinc-900 via-zinc-800 to-black p-8 md:p-12 mb-10 relative overflow-hidden border border-zinc-700">
                <div class="max-w-md">
                    <div class="inline-flex items-center gap-x-2 text-cyan-400 text-sm font-medium mb-4">
                        <div class="w-2 h-2 bg-cyan-400 rounded-full live-dot"></div>
                        A 68 DÍAS DEL INICIO
                    </div>
                    <h2 class="text-5xl md:text-6xl font-semibold logo-font tracking-[-2px] leading-none mb-6">La Copa del Mundo más grande de la historia</h2>
                    <p class="text-zinc-400 text-lg mb-8">48 equipos • 104 partidos • 16 ciudades • 3 países</p>
                    
                    <div class="flex gap-x-4">
                        <button onclick="navigateTo('matches')" 
                                class="bg-white text-zinc-950 hover:bg-cyan-400 hover:text-white px-8 py-4 rounded-3xl font-semibold flex items-center gap-x-3">
                            <i class="fa-solid fa-play"></i>
                            VER PARTIDOS EN VIVO
                        </button>
                        <button onclick="navigateTo('teams')" 
                                class="border border-white/30 hover:border-white/60 px-8 py-4 rounded-3xl font-semibold flex items-center gap-x-3">
                            EXPLORAR EQUIPOS
                        </button>
                    </div>
                </div>

                <!-- Featured match -->
                <div class="absolute bottom-8 right-8 hidden xl:flex bg-zinc-900/90 backdrop-blur-xl rounded-3xl p-6 shadow-2xl border border-cyan-400/20">
                    <div class="text-center">
                        <div class="text-xs text-amber-400 flex items-center justify-center gap-x-1 mb-2">
                            <i class="fa-solid fa-fire"></i> PARTIDO DESTACADO
                        </div>
                        <div class="flex items-center gap-x-8">
                            <div class="text-center">
                                <div class="text-5xl mb-2">🇦🇷</div>
                                <p class="font-medium">Argentina</p>
                            </div>
                            <div>
                                <div class="text-2xl font-mono font-semibold">19:00</div>
                                <div class="text-xs text-zinc-400">11 JUN 2026 • Estadio Azteca</div>
                                <div class="flex items-center justify-center gap-x-2 my-3">
                                    <span class="px-4 py-1 bg-emerald-400 text-emerald-950 rounded-3xl text-sm font-bold">EN VIVO</span>
                                </div>
                            </div>
                            <div class="text-center">
                                <div class="text-5xl mb-2">🇧🇷</div>
                                <p class="font-medium">Brasil</p>
                            </div>
                        </div>
                        <div class="text-cyan-400 text-sm mt-4 font-medium flex items-center justify-center gap-x-2">
                            <i class="fa-solid fa-tv"></i> TRANSMISIÓN EN DIRECTO
                        </div>
                    </div>
                </div>
            </div>

            <!-- Quick stats row -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="bg-zinc-900 rounded-3xl p-6 border border-zinc-700">
                    <p class="text-zinc-400 text-sm">Goles totales</p>
                    <p class="text-5xl font-semibold mt-2">142</p>
                    <p class="text-emerald-400 text-sm flex items-center gap-x-1 mt-4"><i class="fa-solid fa-arrow-trend-up"></i> +18% vs 2022</p>
                </div>
                <div class="bg-zinc-900 rounded-3xl p-6 border border-zinc-700">
                    <p class="text-zinc-400 text-sm">Asistencia promedio</p>
                    <p class="text-5xl font-semibold mt-2">68,420</p>
                    <p class="text-amber-400 text-sm flex items-center gap-x-1 mt-4"><i class="fa-solid fa-users"></i> Récord histórico</p>
                </div>
                <div class="bg-zinc-900 rounded-3xl p-6 border border-zinc-700">
                    <p class="text-zinc-400 text-sm">Mejor jugador actual</p>
                    <div class="flex items-center gap-x-4 mt-4">
                        <span class="text-4xl">🇫🇷</span>
                        <div>
                            <p class="font-semibold">Kylian Mbappé</p>
                            <p class="text-xs text-zinc-400">5 goles • 3 asistencias</p>
                        </div>
                    </div>
                </div>
                <div class="bg-zinc-900 rounded-3xl p-6 border border-zinc-700 flex flex-col justify-between">
                    <p class="text-zinc-400 text-sm">Próximo partido de México</p>
                    <div class="flex items-center justify-between">
                        <div>🇲🇽</div>
                        <div class="text-center">
                            <p class="text-lg font-medium">vs Canadá</p>
                            <p class="text-xs text-cyan-400">16 JUN • 20:00 • Los Ángeles</p>
                        </div>
                        <div>🇨🇦</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SECCIÓN 2: PARTIDOS -->
        <div id="screen-matches" class="section hidden">
            <div class="flex items-center justify-between mb-8">
                <h2 class="text-3xl font-semibold">Partidos en vivo y próximos</h2>
                <button onclick="simulateLiveUpdate()" 
                        class="flex items-center gap-x-2 bg-emerald-500 hover:bg-emerald-600 text-white px-6 py-3 rounded-3xl text-sm font-semibold">
                    <i class="fa-solid fa-rotate-right"></i>
                    ACTUALIZAR EN VIVO
                </button>
            </div>

            <div id="matches-list" class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- JS populated -->
            </div>
        </div>

        <!-- SECCIÓN 3: EQUIPOS -->
        <div id="screen-teams" class="section hidden">
            <h2 class="text-3xl font-semibold mb-8">32 equipos clasificados</h2>
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-4" id="teams-grid">
                <!-- JS populated -->
            </div>
        </div>

        <!-- SECCIÓN 4: CLASIFICACIÓN -->
        <div id="screen-standings" class="section hidden">
            <h2 class="text-3xl font-semibold mb-8">Clasificación por grupos</h2>
            
            <div class="flex gap-x-2 mb-6 border-b border-zinc-700 pb-2 overflow-x-auto">
                <button onclick="showGroup(0)" id="group-tab-0" class="px-6 py-2 bg-white text-zinc-950 rounded-3xl text-sm font-semibold">Grupo A</button>
                <button onclick="showGroup(1)" id="group-tab-1" class="px-6 py-2 hover:bg-zinc-800 rounded-3xl text-sm font-semibold">Grupo B</button>
                <button onclick="showGroup(2)" id="group-tab-2" class="px-6 py-2 hover:bg-zinc-800 rounded-3xl text-sm font-semibold">Grupo C</button>
                <button onclick="showGroup(3)" id="group-tab-3" class="px-6 py-2 hover:bg-zinc-800 rounded-3xl text-sm font-semibold">Grupo D</button>
            </div>

            <div id="standings-table" class="bg-zinc-900 rounded-3xl overflow-hidden">
                <!-- JS populated -->
            </div>
        </div>

        <!-- SECCIÓN 5: ESTADÍSTICAS -->
        <div id="screen-stats" class="section hidden">
            <h2 class="text-3xl font-semibold mb-8">Estadísticas del torneo</h2>
            
            <div class="grid md:grid-cols-2 gap-8">
                <!-- Top goleadores -->
                <div>
                    <h3 class="font-medium text-zinc-400 mb-4 flex items-center gap-x-2"><i class="fa-solid fa-futbol"></i> Goleadores</h3>
                    <div id="top-scorers" class="space-y-4">
                        <!-- JS populated -->
                    </div>
                </div>
                
                <!-- Otras estadísticas -->
                <div class="bg-zinc-900 rounded-3xl p-8">
                    <h3 class="font-medium mb-6">Datos destacados</h3>
                    <div class="space-y-8">
                        <div class="flex justify-between items-end">
                            <div>
                                <p class="text-sm text-zinc-400">Mayor posesión promedio</p>
                                <p class="text-4xl font-semibold">68%</p>
                                <p class="text-emerald-400">España</p>
                            </div>
                            <div class="text-7xl">🇪🇸</div>
                        </div>
                        <div class="flex justify-between items-end">
                            <div>
                                <p class="text-sm text-zinc-400">Más tarjetas rojas</p>
                                <p class="text-4xl font-semibold">7</p>
                                <p class="text-amber-400">Uruguay</p>
                            </div>
                            <div class="text-7xl">🇺🇾</div>
                        </div>
                        <div class="flex justify-between items-end">
                            <div>
                                <p class="text-sm text-zinc-400">Partidos con más goles</p>
                                <p class="text-4xl font-semibold">7 - 3</p>
                                <p class="text-cyan-400">Portugal 7 - 3 Ghana</p>
                            </div>
                            <div class="text-7xl">🇵🇹</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SECCIÓN 6: NOTICIAS -->
        <div id="screen-news" class="section hidden">
            <h2 class="text-3xl font-semibold mb-8">Últimas noticias</h2>
            <div id="news-feed" class="space-y-6">
                <!-- JS populated -->
            </div>
        </div>
    </main>

    <!-- MODAL DETALLE PARTIDO -->
    <div onclick="if(event.target.id === 'match-modal') hideModal()" id="match-modal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-[9999]">
        <div onclick="event.stopImmediatePropagation()" class="modal bg-zinc-900 rounded-3xl max-w-lg w-full mx-4 p-8">
            <div class="flex justify-between items-start mb-8">
                <div>
                    <span id="modal-match-status" class="text-xs px-4 py-1 rounded-3xl"></span>
                    <p id="modal-match-time" class="text-2xl font-medium mt-2"></p>
                </div>
                <button onclick="hideModal()" class="text-3xl leading-none text-zinc-400">×</button>
            </div>
            
            <div class="flex items-center justify-between text-center">
                <div id="modal-team1" class="flex-1"></div>
                <div class="text-center px-8">
                    <div id="modal-score" class="text-6xl font-mono font-bold"></div>
                    <div id="modal-stadium" class="text-xs text-zinc-400 mt-1"></div>
                </div>
                <div id="modal-team2" class="flex-1"></div>
            </div>

            <div class="mt-12 text-sm space-y-4 border-t border-zinc-700 pt-8">
                <div class="flex justify-between"><span class="text-zinc-400">Posesión</span><span id="modal-possession" class="font-medium"></span></div>
                <div class="flex justify-between"><span class="text-zinc-400">Tiros a puerta</span><span id="modal-shots" class="font-medium"></span></div>
                <div class="flex justify-between"><span class="text-zinc-400">Tarjetas amarillas</span><span id="modal-yellows" class="font-medium"></span></div>
                <div class="flex justify-between"><span class="text-zinc-400">Goles esperados (xG)</span><span id="modal-xg" class="font-medium"></span></div>
            </div>
            
            <button onclick="hideModal()" class="w-full mt-10 py-4 bg-white text-zinc-950 rounded-3xl font-semibold">Cerrar</button>
        </div>
    </div>

    <!-- MODAL EQUIPO FAVORITO -->
    <div onclick="if(event.target.id === 'fav-modal') hideFavModal()" id="fav-modal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-[9999]">
        <div onclick="event.stopImmediatePropagation()" class="modal bg-zinc-900 rounded-3xl max-w-md w-full mx-4 p-8">
            <h3 class="text-xl font-semibold mb-6">Elige tu equipo favorito</h3>
            <div class="grid grid-cols-4 gap-4" id="fav-teams-list">
                <!-- JS populated -->
            </div>
            <button onclick="hideFavModal()" class="mt-8 w-full py-4 border border-zinc-700 hover:bg-zinc-800 rounded-3xl">Cerrar</button>
        </div>
    </div>

    <script>
        // Tailwind script activation
        function initializeTailwind() {
            return {
                config(userConfig = {}) {
                    return {
                        content: [],
                        theme: {
                            extend: {},
                        },
                        plugins: [],
                        ...userConfig,
                    }
                },
                theme: {
                    extend: {},
                },
            }
        }
        
        // Datos del torneo (puedes modificar libremente)
        const tournamentData = {
            favoriteTeam: {
                name: "México",
                flag: "🇲🇽",
                code: "MEX"
            },
            
            matches: [
                {
                    id: 1,
                    home: { name: "Argentina", flag: "🇦🇷" },
                    away: { name: "Brasil", flag: "🇧🇷" },
                    time: "19:00",
                    date: "11 JUN",
                    stadium: "Estadio Azteca, CDMX",
                    status: "live",
                    score: "2 - 1",
                    live: true
                },
                {
                    id: 2,
                    home: { name: "México", flag: "🇲🇽" },
                    away: { name: "Canadá", flag: "🇨🇦" },
                    time: "20:00",
                    date: "16 JUN",
                    stadium: "SoFi Stadium, Los Ángeles",
                    status: "upcoming",
                    score: "0 - 0"
                },
                {
                    id: 3,
                    home: { name: "Francia", flag: "🇫🇷" },
                    away: { name: "España", flag: "🇪🇸" },
                    time: "17:00",
                    date: "12 JUN",
                    stadium: "MetLife Stadium, Nueva York",
                    status: "finished",
                    score: "3 - 2"
                },
                {
                    id: 4,
                    home: { name: "Alemania", flag: "🇩🇪" },
                    away: { name: "Inglaterra", flag: "🏴󠁧󠁢󠁥󠁮󠁧󠁿" },
                    time: "14:00",
                    date: "15 JUN",
                    stadium: "BC Place, Vancouver",
                    status: "live",
                    score: "1 - 1",
                    live: true
                }
            ],
            
            teams: [
                { name: "México", flag: "🇲🇽", group: "A" },
                { name: "Argentina", flag: "🇦🇷", group: "A" },
                { name: "Brasil", flag: "🇧🇷", group: "B" },
                { name: "Francia", flag: "🇫🇷", group: "B" },
                { name: "España", flag: "🇪🇸", group: "C" },
                { name: "Alemania", flag: "🇩🇪", group: "C" },
                { name: "Inglaterra", flag: "🏴󠁧󠁢󠁥󠁮󠁧󠁿", group: "D" },
                { name: "Portugal", flag: "🇵🇹", group: "D" },
                { name: "Estados Unidos", flag: "🇺🇸", group: "A" },
                { name: "Canadá", flag: "🇨🇦", group: "A" },
                { name: "Países Bajos", flag: "🇳🇱", group: "E" },
                { name: "Italia", flag: "🇮🇹", group: "E" },
                { name: "Uruguay", flag: "🇺🇾", group: "F" },
                { name: "Croacia", flag: "🇭🇷", group: "F" },
                { name: "Japón", flag: "🇯🇵", group: "G" },
                { name: "Corea del Sur", flag: "🇰🇷", group: "G" }
            ],
            
            groups: {
                0: { // Grupo A
                    name: "Grupo A",
                    standings: [
                        { pos: 1, team: "🇦🇷 Argentina", pts: 9, pj: 3, gf: 8, gc: 2 },
                        { pos: 2, team: "🇲🇽 México", pts: 6, pj: 3, gf: 5, gc: 3 },
                        { pos: 3, team: "🇺🇸 Estados Unidos", pts: 3, pj: 3, gf: 4, gc: 5 },
                        { pos: 4, team: "🇨🇦 Canadá", pts: 0, pj: 3, gf: 1, gc: 8 }
                    ]
                },
                1: { // Grupo B
                    name: "Grupo B",
                    standings: [
                        { pos: 1, team: "🇧🇷 Brasil", pts: 7, pj: 3, gf: 7, gc: 3 },
                        { pos: 2, team: "🇫🇷 Francia", pts: 6, pj: 3, gf: 6, gc: 4 },
                        { pos: 3, team: "🇵🇹 Portugal", pts: 4, pj: 3, gf: 5, gc: 5 },
                        { pos: 4, team: "🇨🇦 Canadá", pts: 0, pj: 3, gf: 2, gc: 8 }
                    ]
                }
            },
            
            topScorers: [
                { name: "Kylian Mbappé", country: "🇫🇷", goals: 7 },
                { name: "Lautaro Martínez", country: "🇦🇷", goals: 5 },
                { name: "Harry Kane", country: "🏴󠁧󠁢󠁥󠁮󠁧󠁿", goals: 5 },
                { name: "Vinicius Jr.", country: "🇧🇷", goals: 4 },
                { name: "Santiago Giménez", country: "🇲🇽", goals: 4 }
            ],
            
            news: [
                {
                    title: "México clasifica a octavos con goleada histórica",
                    subtitle: "La Selección Azteca vence 4-0 a Canadá y lidera su grupo",
                    time: "hace 2 horas"
                },
                {
                    title: "Mbappé rompe récord de goles en una fase de grupos",
                    subtitle: "El francés ya suma 7 tantos en el torneo",
                    time: "hace 5 horas"
                },
                {
                    title: "Estadio Azteca bate récord de asistencia",
                    subtitle: "132,458 aficionados presenciaron México vs Argentina",
                    time: "ayer"
                }
            ]
        }

        // Renderizar partidos
        function renderMatches() {
            const container = document.getElementById('matches-list')
            container.innerHTML = ''
            
            tournamentData.matches.forEach(match => {
                const cardHTML = `
                <div onclick="showMatchDetail(${match.id})" class="card-hover bg-zinc-900 border border-zinc-700 hover:border-cyan-400/30 rounded-3xl p-6 cursor-pointer">
                    <div class="flex justify-between items-center mb-4">
                        <div class="text-xs font-medium uppercase tracking-widest ${match.live ? 'text-emerald-400' : 'text-zinc-400'}">
                            ${match.live ? '<span class="inline-block w-2 h-2 bg-emerald-400 rounded-full live-dot mr-1"></span> EN VIVO' : match.status === 'finished' ? 'FINALIZADO' : match.date}
                        </div>
                        <div class="text-xs text-zinc-400">${match.time}</div>
                    </div>
                    
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-x-4">
                            <span class="text-4xl">${match.home.flag}</span>
                            <span class="font-semibold">${match.home.name}</span>
                        </div>
                        <div class="text-center">
                            <div class="font-mono text-4xl font-bold">${match.score}</div>
                        </div>
                        <div class="flex items-center gap-x-4 flex-row-reverse">
                            <span class="text-4xl">${match.away.flag}</span>
                            <span class="font-semibold">${match.away.name}</span>
                        </div>
                    </div>
                    
                    <div class="text-center text-xs text-zinc-400 mt-6">${match.stadium}</div>
                </div>`
                container.innerHTML += cardHTML
            })
        }

        // Renderizar equipos
        function renderTeams() {
            const container = document.getElementById('teams-grid')
            container.innerHTML = ''
            
            tournamentData.teams.forEach(team => {
                const isFavorite = team.name === tournamentData.favoriteTeam.name
                
                const cardHTML = `
                <div onclick="viewTeam('${team.name}')" class="card-hover bg-zinc-900 border ${isFavorite ? 'border-cyan-400' : 'border-zinc-700'} hover:border-cyan-400 rounded-3xl p-6 flex flex-col items-center text-center cursor-pointer">
                    <div class="text-6xl mb-4">${team.flag}</div>
                    <p class="font-semibold text-lg">${team.name}</p>
                    <p class="text-xs text-zinc-400 mt-1">Grupo ${team.group}</p>
                    ${isFavorite ? `<div class="mt-4 text-[10px] bg-cyan-400 text-zinc-950 px-4 py-1 rounded-3xl font-bold inline-flex items-center">⭐ TU EQUIPO</div>` : ''}
                </div>`
                container.innerHTML += cardHTML
            })
        }

        // Renderizar tabla de posiciones
        let currentGroup = 0
        function showGroup(groupIndex) {
            currentGroup = groupIndex
            // Reset tabs
            document.querySelectorAll('[id^="group-tab-"]').forEach(el => el.classList.remove('bg-white', 'text-zinc-950'))
            document.getElementById(`group-tab-${groupIndex}`).classList.add('bg-white', 'text-zinc-950')
            
            const container = document.getElementById('standings-table')
            const group = tournamentData.groups[groupIndex]
            
            let html = `
            <div class="px-8 pt-8 pb-4">
                <h3 class="text-xl font-semibold">${group.name}</h3>
            </div>
            <table class="w-full">
                <thead>
                    <tr class="text-xs text-zinc-400 border-b border-zinc-700">
                        <th class="text-left pl-8 py-4">POS</th>
                        <th class="text-left py-4">EQUIPO</th>
                        <th class="text-center py-4">PJ</th>
                        <th class="text-center py-4">GF</th>
                        <th class="text-center py-4">GC</th>
                        <th class="text-center py-4 font-bold">PTS</th>
                    </tr>
                </thead>
                <tbody>`
            
            group.standings.forEach(row => {
                html += `
                <tr class="border-b border-zinc-700 last:border-none hover:bg-zinc-800/50">
                    <td class="pl-8 py-5 font-medium">${row.pos}</td>
                    <td class="py-5 font-medium">${row.team}</td>
                    <td class="text-center py-5">${row.pj}</td>
                    <td class="text-center py-5">${row.gf}</td>
                    <td class="text-center py-5">${row.gc}</td>
                    <td class="text-center py-5 font-bold text-cyan-400">${row.pts}</td>
                </tr>`
            })
            
            html += `</tbody></table>`
            container.innerHTML = html
        }

        // Renderizar goleadores
        function renderTopScorers() {
            const container = document.getElementById('top-scorers')
            container.innerHTML = ''
            
            tournamentData.topScorers.forEach((player, i) => {
                const html = `
                <div class="flex justify-between items-center bg-zinc-900 border border-zinc-700 rounded-3xl px-6 py-5">
                    <div class="flex items-center gap-x-4">
                        <span class="text-4xl">${player.country}</span>
                        <div>
                            <p class="font-medium">${player.name}</p>
                            <p class="text-xs text-zinc-400">Goleador ${i + 1}</p>
                        </div>
                    </div>
                    <div class="text-right">
                        <p class="text-4xl font-mono font-bold">${player.goals}</p>
                        <p class="text-xs uppercase tracking-widest text-emerald-400">GOLES</p>
                    </div>
                </div>`
                container.innerHTML += html
            })
        }

        // Renderizar noticias
        function renderNews() {
            const container = document.getElementById('news-feed')
            container.innerHTML = ''
            
            tournamentData.news.forEach(item => {
                const html = `
                <div class="bg-zinc-900 border border-zinc-700 rounded-3xl p-6 flex gap-6">
                    <div class="flex-1">
                        <h4 class="font-semibold text-xl leading-tight">${item.title}</h4>
                        <p class="text-zinc-400 mt-3">${item.subtitle}</p>
                        <p class="text-xs text-cyan-400 mt-6">${item.time}</p>
                    </div>
                    <div class="hidden sm:flex w-32 h-32 bg-gradient-to-br from-cyan-400/10 to-transparent rounded-3xl items-center justify-center text-7xl flex-shrink-0">📰</div>
                </div>`
                container.innerHTML += html
            })
        }

        // Mostrar detalle de partido
        function showMatchDetail(id) {
            const match = tournamentData.matches.find(m => m.id === id)
            if (!match) return
            
            const modal = document.getElementById('match-modal')
            
            document.getElementById('modal-match-status').innerHTML = match.live 
                ? `<span class="bg-emerald-400 text-emerald-950 px-4 py-1 rounded-3xl flex items-center w-fit"><span class="live-dot w-2 h-2 bg-emerald-950 inline-block mr-2"></span>EN VIVO</span>` 
                : match.status === 'finished' ? `<span class="bg-zinc-700 px-4 py-1 rounded-3xl">FINALIZADO</span>` : `<span class="bg-amber-400 text-amber-950 px-4 py-1 rounded-3xl">PRÓXIMAMENTE</span>`
            
            document.getElementById('modal-match-time').innerHTML = `${match.date} • ${match.time}`
            
            // Team 1
            document.getElementById('modal-team1').innerHTML = `
                <div class="text-7xl mb-3">${match.home.flag}</div>
                <p class="text-2xl font-semibold">${match.home.name}</p>`
            
            // Team 2
            document.getElementById('modal-team2').innerHTML = `
                <div class="text-7xl mb-3">${match.away.flag}</div>
                <p class="text-2xl font-semibold">${match.away.name}</p>`
            
            document.getElementById('modal-score').textContent = match.score
            document.getElementById('modal-stadium').innerHTML = `<i class="fa-solid fa-location-dot mr-1"></i> ${match.stadium}`
            
            // Stats simuladas
            document.getElementById('modal-possession').innerHTML = `${match.home.name}: 53% • ${match.away.name}: 47%`
            document.getElementById('modal-shots').innerHTML = `8 - 11`
            document.getElementById('modal-yellows').innerHTML = `2 - 4`
            document.getElementById('modal-xg').innerHTML = `1.8 - 2.3`
            
            modal.classList.remove('hidden')
            modal.classList.add('flex')
        }

        function hideModal() {
            const modal = document.getElementById('match-modal')
            modal.classList.add('hidden')
            modal.classList.remove('flex')
        }

        // Simular actualización en vivo
        function simulateLiveUpdate() {
            // Actualizar algunos scores aleatoriamente
            tournamentData.matches.forEach(match => {
                if (match.live) {
                    const homeScore = parseInt(match.score.split(' - ')[0])
                    const awayScore = parseInt(match.score.split(' - ')[1])
                    match.score = `${homeScore + Math.floor(Math.random() * 2)} - ${awayScore + Math.floor(Math.random() * 2)}`
                }
            })
            
            renderMatches()
            
            // Toast temporal
            const toast = document.createElement('div')
            toast.style.cssText = 'position:fixed; bottom:20px; right:20px; background:#00d4ff; color:#000; padding:16px 24px; border-radius:9999px; box-shadow:0 10px 15px -3px rgb(0 212 255); font-weight:600;'
            toast.innerHTML = '✅ Marcadores actualizados en tiempo real'
            document.body.appendChild(toast)
            
            setTimeout(() => {
                toast.style.transition = 'all 0.4s cubic-bezier(0.4, 0, 1, 1)'
                toast.style.transform = 'translateY(100px)'
                toast.style.opacity = '0'
                setTimeout(() => toast.remove(), 400)
            }, 2500)
        }

        // Ver equipo individual (modal simple)
        function viewTeam(name) {
            const team = tournamentData.teams.find(t => t.name === name)
            if (!team) return
            
            const message = `Perfil de ${team.name}\n\nGrupo: ${team.group}\nEstadio local: ${name === 'México' ? 'Estadio Azteca' : 'Varios'}\nPróximo partido: En vivo pronto\n\n¡Sigue su camino hacia la final!`
            alert(message) // En una app real usaríamos un modal más elaborado
        }

        // Modal de equipo favorito
        function showFavoriteModal() {
            const modal = document.getElementById('fav-modal')
            const container = document.getElementById('fav-teams-list')
            container.innerHTML = ''
            
            tournamentData.teams.slice(0, 12).forEach(team => {
                const html = `
                <div onclick="setFavoriteTeam('${team.name}', '${team.flag}')" class="flex flex-col items-center cursor-pointer hover:scale-110">
                    <div class="text-5xl mb-2">${team.flag}</div>
                    <p class="text-xs font-medium text-center">${team.name}</p>
                </div>`
                container.innerHTML += html
            })
            
            modal.style.display = 'flex'
        }
        
        function hideFavModal() {
            const modal = document.getElementById('fav-modal')
            modal.style.display = 'none'
        }
        
        function setFavoriteTeam(name, flag) {
            tournamentData.favoriteTeam.name = name
            tournamentData.favoriteTeam.flag = flag
            
            // Actualizar UI
            document.getElementById('favorite-flag').textContent = flag
            document.getElementById('favorite-name').textContent = name
            
            hideFavModal()
            renderTeams() // Refrescar lista de equipos
        }
        
        // Notificación falsa
        function fakeNotification() {
            const badge = document.getElementById('notification-badge')
            badge.textContent = '1'
            
            const notif = document.createElement('div')
            notif.style.cssText = 'position:fixed; top:80px; right:20px; background:#111827; border:1px solid #00d4ff; padding:20px; border-radius:24px; width:280px; box-shadow:25px 25px 50px -12px rgb(0 212 255);'
            notif.innerHTML = `
                <div class="flex gap-3">
                    <span class="text-3xl">🏆</span>
                    <div>
                        <p class="font-medium">¡México gana su partido!</p>
                        <p class="text-sm text-zinc-400 mt-1">4 - 0 vs Canadá • Avanza a octavos</p>
                    </div>
                </div>`
            document.body.appendChild(notif)
            
            setTimeout(() => {
                notif.style.transitionDuration = '400ms'
                notif.style.opacity = '0'
                setTimeout(() => notif.remove(), 400)
                badge.textContent = '3'
            }, 3200)
        }
        
        function showProfile() {
            alert('👋 ¡Hola Sofía! Tu equipo favorito es México y has visto 12 partidos en la app.\n\nEstadística personal: 87% de aciertos en predicciones.')
        }
        
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu')
            const icon = document.getElementById('mobile-icon')
            
            if (menu.classList.contains('hidden')) {
                menu.style.display = 'block'
                icon.classList.replace('fa-bars', 'fa-xmark')
            } else {
                menu.style.display = 'none'
                icon.classList.replace('fa-xmark', 'fa-bars')
            }
        }
        
        // Navegación entre secciones
        function navigateTo(screen) {
            // Ocultar todas
            document.querySelectorAll('.section').forEach(s => s.classList.add('hidden'))
            
            // Mostrar la solicitada
            const target = document.getElementById(`screen-${screen}`)
            if (target) target.classList.remove('hidden')
            
            // Actualizar nav
            document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'))
            const activeNav = document.getElementById(`nav-${screen}`)
            if (activeNav) activeNav.classList.add('active')
            
            // Renderizar contenido si es necesario
            if (screen === 'matches') renderMatches()
            else if (screen === 'teams') renderTeams()
            else if (screen === 'standings') showGroup(0)
            else if (screen === 'stats') renderTopScorers()
            else if (screen === 'news') renderNews()
        }
        
        // Inicialización completa
        function initApp() {
            initializeTailwind()
            
            // Render inicial
            renderMatches()
            renderTeams()
            showGroup(0)
            renderTopScorers()
            renderNews()
            
            console.log('%c✅ App Mundial 2026 cargada con éxito. ¡Disfruta el torneo!', 'background:#00d4ff;color:#000;padding:4px 8px;border-radius:4px;font-size:13px')
            
            // Actualización automática cada 45 segundos (simulación de live)
            setInterval(() => {
                if (document.getElementById('screen-matches').classList.contains('hidden') === false) {
                    // Solo actualizar si estamos en la pantalla de partidos
                    simulateLiveUpdate()
                }
            }, 45000)
            
            console.log('📍 Ubicación detectada: Ciudad de México • ¡Viva México!')
        }
        
        // Arrancar la app
        window.onload = initApp
    </script>
</body>
</html>
