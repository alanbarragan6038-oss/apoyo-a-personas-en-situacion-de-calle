<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Refugio Seguro - Plataforma de Donaciones</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <style>
        /* Animaciones personalizadas para los modales */
        @keyframes zoomIn {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }
        @keyframes slideUp {
            from { opacity: 0; transform: translateY(2rem); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-zoom-in {
            animation: zoomIn 0.2s ease-out forwards;
        }
        .animate-slide-up {
            animation: slideUp 0.3s ease-out forwards;
        }
        
        /* Ocultar flechas del input number */
        input[type="number"]::-webkit-inner-spin-button,
        input[type="number"]::-webkit-outer-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }
        input[type="number"] {
            -moz-appearance: textfield;
        }
    </style>
</head>
<body class="min-h-screen bg-slate-50 font-sans text-slate-800">

    <!-- Navbar -->
    <nav class="sticky top-0 z-40 w-full bg-white/95 backdrop-blur-md border-b border-slate-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center gap-3 cursor-pointer">
                    <div class="bg-blue-600 p-2.5 rounded-xl text-white shadow-lg shadow-blue-200">
                        <i data-lucide="heart" class="w-6 h-6 animate-pulse"></i>
                    </div>
                    <span class="font-extrabold text-2xl tracking-tight text-slate-900">Refugio<span class="text-blue-600">Seguro</span></span>
                </div>
                <div class="hidden lg:flex items-center space-x-8">
                    <a href="#quienes-somos" class="text-sm font-bold text-slate-500 hover:text-blue-600 transition-colors">Quiénes Somos</a>
                    <a href="#que-hacemos" class="text-sm font-bold text-slate-500 hover:text-blue-600 transition-colors">Qué Hacemos</a>
                    <a href="#transparencia" class="text-sm font-bold text-slate-500 hover:text-blue-600 transition-colors">Cero Desvío de Fondos</a>
                    <a href="#tecnologia" class="text-sm font-bold text-slate-500 hover:text-blue-600 transition-colors">Tecnología</a>
                </div>
                <div>
                    <button onclick="openDonateModal()" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-full font-bold shadow-xl shadow-blue-500/30 transition-all hover:scale-105 active:scale-95 flex items-center gap-2">
                        <i data-lucide="heart" class="w-[18px] h-[18px]"></i>
                        Donar Ahora
                    </button>
                </div>
            </div>
        </div>
    </nav>

    <main>
        <!-- Hero Section -->
        <section class="relative bg-slate-900 text-white overflow-hidden">
            <div class="absolute inset-0 z-0">
                <img src="https://images.unsplash.com/photo-1542367787-4baf35f3037d?auto=format&fit=crop&q=80&w=2000" alt="Personas ayudando a comunidad" class="w-full h-full object-cover opacity-25">
                <div class="absolute inset-0 bg-gradient-to-r from-slate-900 via-slate-900/90 to-transparent"></div>
            </div>
            <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-24 md:py-36">
                <div class="max-w-3xl">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-blue-500/20 text-blue-300 border border-blue-500/30 mb-8 text-sm font-bold backdrop-blur-sm">
                        <i data-lucide="shield-check" class="w-[18px] h-[18px]"></i>
                        Pagos 100% Seguros y Transparentes
                    </div>
                    <h1 class="text-5xl md:text-7xl font-black tracking-tight mb-8 leading-tight">
                        Ayuda real. <br>
                        <span class="text-blue-400">Impacto verificable.</span>
                    </h1>
                    <p class="text-xl text-slate-300 mb-12 max-w-2xl leading-relaxed">
                        Rescatamos a personas en situación de calle brindando refugio, alimento y atención. Nuestra plataforma garantiza que cada peso que donas llegue a su destino, sin intermediarios.
                    </p>
                    <div class="flex flex-col sm:flex-row gap-5">
                        <button onclick="openDonateModal()" class="bg-blue-600 hover:bg-blue-500 text-white px-8 py-4 rounded-full font-bold text-lg shadow-2xl shadow-blue-600/40 transition-all flex items-center justify-center gap-2 hover:-translate-y-1">
                            Hacer una Donación <i data-lucide="chevron-right" class="w-5 h-5"></i>
                        </button>
                        <a href="#transparencia" class="bg-white/10 hover:bg-white/20 text-white px-8 py-4 rounded-full font-bold text-lg backdrop-blur-sm border border-white/20 transition-all flex items-center justify-center gap-2 hover:-translate-y-1">
                            <i data-lucide="activity" class="w-5 h-5"></i> Ver Transparencia
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Us Section -->
        <section id="quienes-somos" class="py-24 bg-white border-b border-slate-100">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid md:grid-cols-2 gap-16 items-center">
                    <div>
                        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-blue-100 text-blue-700 mb-6 text-sm font-bold uppercase tracking-wide">
                            <i data-lucide="heart-handshake" class="w-4 h-4"></i> Quiénes Somos
                        </div>
                        <h2 class="text-4xl font-black text-slate-900 mb-6 leading-tight">La conexión directa entre tu empatía y quienes más lo necesitan.</h2>
                        <p class="text-slate-600 text-lg mb-6 leading-relaxed">
                            Somos una organización civil formada por médicos, trabajadores sociales y voluntarios unidos por una causa común: erradicar la indiferencia hacia las personas en situación de calle.
                        </p>
                        <p class="text-slate-600 text-lg mb-8 leading-relaxed">
                            Nacimos con la firme convicción de que la ayuda debe ser directa, eficiente y 100% transparente. <strong>No somos intermediarios burocráticos</strong>; somos operadores en el campo asegurando que tu ayuda se convierta en platos de comida y noches bajo techo.
                        </p>
                        <div class="flex flex-wrap gap-6">
                            <div class="flex items-center gap-3 bg-slate-50 px-4 py-3 rounded-xl border border-slate-200">
                                <i data-lucide="users" class="w-6 h-6 text-blue-600"></i>
                                <span class="font-bold text-slate-800">+500 Voluntarios</span>
                            </div>
                            <div class="flex items-center gap-3 bg-slate-50 px-4 py-3 rounded-xl border border-slate-200">
                                <i data-lucide="award" class="w-6 h-6 text-blue-600"></i>
                                <span class="font-bold text-slate-800">ONG Certificada</span>
                            </div>
                        </div>
                    </div>
                    <div class="relative rounded-3xl overflow-hidden shadow-2xl h-[500px]">
                        <img src="https://images.unsplash.com/photo-1593113563332-f1443126f555?auto=format&fit=crop&q=80&w=1000" alt="Equipo de voluntarios trabajando en comunidad" class="w-full h-full object-cover hover:scale-105 transition-transform duration-700">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-900/50 to-transparent"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Project Section -->
        <section id="que-hacemos" class="py-24 bg-slate-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-3xl mx-auto mb-20">
                    <h2 class="text-4xl font-black text-slate-900 mb-6">¿Qué hacemos exactamente?</h2>
                    <p class="text-slate-600 text-xl leading-relaxed">
                        Refugio Seguro no es solo caridad, es un camino hacia la reintegración. Tu donación financia directamente estos tres pilares operativos.
                    </p>
                </div>

                <div class="grid md:grid-cols-3 gap-8">
                    <div class="bg-white p-10 rounded-3xl shadow-lg border border-slate-100 hover:-translate-y-2 transition-transform duration-300">
                        <div class="w-16 h-16 bg-blue-100 text-blue-600 rounded-2xl flex items-center justify-center mb-8 shadow-inner">
                            <i data-lucide="home" class="w-8 h-8"></i>
                        </div>
                        <h3 class="text-2xl font-black text-slate-900 mb-4">Refugio y Alimento</h3>
                        <p class="text-slate-600 leading-relaxed">
                            Proporcionamos camas seguras, duchas con agua caliente y tres comidas calientes y nutritivas al día para quitar el hambre inmediata.
                        </p>
                    </div>
                    <div class="bg-white p-10 rounded-3xl shadow-lg border border-slate-100 hover:-translate-y-2 transition-transform duration-300">
                        <div class="w-16 h-16 bg-emerald-100 text-emerald-600 rounded-2xl flex items-center justify-center mb-8 shadow-inner">
                            <i data-lucide="activity" class="w-8 h-8"></i>
                        </div>
                        <h3 class="text-2xl font-black text-slate-900 mb-4">Atención Médica</h3>
                        <p class="text-slate-600 leading-relaxed">
                            Desplegamos clínicas móviles y psicólogos que ofrecen atención primaria, medicamentos y salud mental accesible en las calles.
                        </p>
                    </div>
                    <div class="bg-white p-10 rounded-3xl shadow-lg border border-slate-100 hover:-translate-y-2 transition-transform duration-300">
                        <div class="w-16 h-16 bg-purple-100 text-purple-600 rounded-2xl flex items-center justify-center mb-8 shadow-inner">
                            <i data-lucide="users" class="w-8 h-8"></i>
                        </div>
                        <h3 class="text-2xl font-black text-slate-900 mb-4">Reintegración</h3>
                        <p class="text-slate-600 leading-relaxed">
                            Ejecutamos programas de capacitación laboral, talleres de oficios y asistencia legal para la obtención de documentos de identidad.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Transparency Section -->
        <section id="transparencia" class="py-24 bg-white border-y border-slate-200">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-4xl mx-auto mb-20">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-emerald-100 text-emerald-800 mb-6 text-sm font-black uppercase tracking-wider">
                        <i data-lucide="pie-chart" class="w-[18px] h-[18px]"></i> Garantía de Cero Desvío de Fondos
                    </div>
                    <h2 class="text-4xl font-black text-slate-900 mb-6">El rastro de tu dinero es público</h2>
                    <p class="text-slate-600 text-xl leading-relaxed">
                        Garantizamos que el 100% de tu aportación llega a su destino. Nuestro sistema de trazabilidad pública impide que los fondos se desvíen. Tú tienes el control y la visibilidad de cada centavo.
                    </p>
                </div>

                <div class="grid lg:grid-cols-2 gap-12">
                    <!-- Gráfico de Uso de Fondos -->
                    <div class="bg-slate-50 p-10 rounded-3xl shadow-sm border border-slate-200">
                        <h3 class="text-2xl font-black text-slate-900 mb-8 flex items-center gap-3">
                            <i data-lucide="bar-chart-3" class="w-7 h-7 text-blue-600"></i> Uso Actual de Donaciones
                        </h3>
                        
                        <div class="space-y-8">
                            <div>
                                <div class="flex justify-between mb-3 text-sm font-bold">
                                    <span class="text-slate-700">Refugio y Alimentos (Directo)</span>
                                    <span class="text-blue-600 text-lg">65%</span>
                                </div>
                                <div class="w-full bg-slate-200 rounded-full h-4">
                                    <div class="bg-blue-600 h-4 rounded-full" style="width: 65%"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-3 text-sm font-bold">
                                    <span class="text-slate-700">Atención Médica y Medicinas</span>
                                    <span class="text-emerald-500 text-lg">25%</span>
                                </div>
                                <div class="w-full bg-slate-200 rounded-full h-4">
                                    <div class="bg-emerald-500 h-4 rounded-full" style="width: 25%"></div>
                                </div>
                            </div>

                            <div>
                                <div class="flex justify-between mb-3 text-sm font-bold">
                                    <span class="text-slate-700">Programas de Reintegración</span>
                                    <span class="text-purple-500 text-lg">10%</span>
                                </div>
                                <div class="w-full bg-slate-200 rounded-full h-4">
                                    <div class="bg-purple-500 h-4 rounded-full" style="width: 10%"></div>
                                </div>
                            </div>
                        </div>

                        <div class="mt-10 p-5 bg-emerald-50 rounded-2xl border border-emerald-200 flex gap-4 items-start">
                            <i data-lucide="shield-check" class="w-7 h-7 text-emerald-600 flex-shrink-0 mt-1"></i>
                            <div>
                                <h4 class="font-bold text-emerald-900 mb-1">0% Gastos Administrativos Ocultos</h4>
                                <p class="text-sm text-emerald-800 leading-relaxed">
                                    Los costos de operación de la plataforma son cubiertos por donantes corporativos específicos. Tu donación ciudadana va 100% al trabajo de campo.
                                </p>
                            </div>
                        </div>
                    </div>

                    <!-- Ledger / Libro Mayor Público -->
                    <div class="bg-slate-900 p-10 rounded-3xl shadow-xl text-white">
                        <div class="flex justify-between items-center mb-8 border-b border-slate-700 pb-6">
                            <h3 class="text-2xl font-black flex items-center gap-3">
                                <i data-lucide="globe" class="w-7 h-7 text-blue-400"></i> Libro Mayor Público
                            </h3>
                            <div class="flex items-center gap-2 text-sm font-bold text-emerald-400 bg-emerald-400/10 px-3 py-1.5 rounded-full">
                                <span class="flex h-2.5 w-2.5 relative">
                                    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                                    <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
                                </span>
                                En vivo
                            </div>
                        </div>

                        <div class="overflow-x-auto">
                            <table class="w-full text-left text-sm">
                                <thead>
                                    <tr class="text-slate-400 border-b border-slate-700">
                                        <th class="pb-4 font-bold uppercase tracking-wider">Donante / Hash</th>
                                        <th class="pb-4 font-bold uppercase tracking-wider">Monto</th>
                                        <th class="pb-4 font-bold uppercase tracking-wider">Destino</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-slate-800">
                                    <tr class="hover:bg-slate-800/50 transition-colors">
                                        <td class="py-5">
                                            <div class="font-bold text-slate-200">María G.</div>
                                            <div class="text-xs text-slate-500 font-mono mt-1">TXN-8472</div>
                                        </td>
                                        <td class="py-5 text-emerald-400 font-black text-lg">$500 MXN</td>
                                        <td class="py-5">
                                            <span class="bg-blue-500/20 text-blue-300 px-3 py-1 rounded-full text-xs font-bold border border-blue-500/30">Alimentos</span>
                                            <div class="text-xs text-slate-500 mt-2">Hace 10 min</div>
                                        </td>
                                    </tr>
                                    <tr class="hover:bg-slate-800/50 transition-colors">
                                        <td class="py-5">
                                            <div class="font-bold text-slate-200">Anónimo</div>
                                            <div class="text-xs text-slate-500 font-mono mt-1">TXN-8471</div>
                                        </td>
                                        <td class="py-5 text-emerald-400 font-black text-lg">$1200 MXN</td>
                                        <td class="py-5">
                                            <span class="bg-blue-500/20 text-blue-300 px-3 py-1 rounded-full text-xs font-bold border border-blue-500/30">Refugio</span>
                                            <div class="text-xs text-slate-500 mt-2">Hace 45 min</div>
                                        </td>
                                    </tr>
                                    <tr class="hover:bg-slate-800/50 transition-colors">
                                        <td class="py-5">
                                            <div class="font-bold text-slate-200">Carlos T.</div>
                                            <div class="text-xs text-slate-500 font-mono mt-1">TXN-8470</div>
                                        </td>
                                        <td class="py-5 text-emerald-400 font-black text-lg">$250 MXN</td>
                                        <td class="py-5">
                                            <span class="bg-blue-500/20 text-blue-300 px-3 py-1 rounded-full text-xs font-bold border border-blue-500/30">Salud</span>
                                            <div class="text-xs text-slate-500 mt-2">Hace 2 horas</div>
                                        </td>
                                    </tr>
                                    <tr class="hover:bg-slate-800/50 transition-colors">
                                        <td class="py-5">
                                            <div class="font-bold text-slate-200">Empresa XYZ</div>
                                            <div class="text-xs text-slate-500 font-mono mt-1">TXN-8469</div>
                                        </td>
                                        <td class="py-5 text-emerald-400 font-black text-lg">$5000 MXN</td>
                                        <td class="py-5">
                                            <span class="bg-blue-500/20 text-blue-300 px-3 py-1 rounded-full text-xs font-bold border border-blue-500/30">General</span>
                                            <div class="text-xs text-slate-500 mt-2">Hace 5 horas</div>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                        <button class="w-full mt-6 py-4 bg-white/5 hover:bg-white/10 rounded-xl text-sm text-white font-bold transition-colors">
                            Explorar todas las transacciones
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Technology Section -->
        <section id="tecnologia" class="py-24 bg-slate-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid md:grid-cols-2 gap-16 items-center">
                    <div>
                        <h2 class="text-4xl font-black text-slate-900 mb-8">La tecnología detrás de tu confianza</h2>
                        <p class="text-slate-600 text-xl mb-10 leading-relaxed">
                            Utilizamos arquitectura moderna de datos para asegurar el pago y automatizar la rendición de cuentas. Sin cajas negras.
                        </p>
                        <ul class="space-y-8">
                            <li class="flex gap-5 items-start">
                                <div class="bg-blue-100 p-3 rounded-2xl text-blue-600 shadow-inner">
                                    <i data-lucide="lock" class="w-7 h-7"></i>
                                </div>
                                <div>
                                    <h4 class="text-xl font-bold text-slate-900 mb-2">Pasarela Encriptada Nivel Bancario</h4>
                                    <p class="text-slate-600">Tus datos financieros nunca tocan nuestros servidores. Procesamos mediante tokens SSL bajo la estricta normativa PCI-DSS nivel 1.</p>
                                </div>
                            </li>
                            <li class="flex gap-5 items-start">
                                <div class="bg-emerald-100 p-3 rounded-2xl text-emerald-600 shadow-inner">
                                    <i data-lucide="file-text" class="w-7 h-7"></i>
                                </div>
                                <div>
                                    <h4 class="text-xl font-bold text-slate-900 mb-2">Trazabilidad Inmutable</h4>
                                    <p class="text-slate-600">Al donar, se genera un Hash (ID único) en nuestra base de datos auditable. Puedes usar tu ticket para ver exactamente en qué factura se gastó tu aporte.</p>
                                </div>
                            </li>
                            <li class="flex gap-5 items-start">
                                <div class="bg-purple-100 p-3 rounded-2xl text-purple-600 shadow-inner">
                                    <i data-lucide="check-circle" class="w-7 h-7"></i>
                                </div>
                                <div>
                                    <h4 class="text-xl font-bold text-slate-900 mb-2">Auditoría Automatizada</h4>
                                    <p class="text-slate-600">El sistema cruza automáticamente los ingresos con los recibos de proveedores (supermercados, farmacias), bloqueando cualquier gasto no autorizado.</p>
                                </div>
                            </li>
                        </ul>
                    </div>
                    
                    <!-- Terminal simulada -->
                    <div class="bg-[#0f172a] p-8 rounded-3xl shadow-2xl relative overflow-hidden border border-slate-700">
                        <div class="absolute -top-24 -right-24 w-64 h-64 bg-blue-600 rounded-full blur-3xl opacity-20"></div>
                        <div class="absolute -bottom-24 -left-24 w-64 h-64 bg-emerald-500 rounded-full blur-3xl opacity-10"></div>
                        
                        <div class="relative z-10 font-mono text-sm">
                            <div class="flex gap-2 mb-6 border-b border-slate-700 pb-4">
                                <div class="w-3.5 h-3.5 rounded-full bg-red-500"></div>
                                <div class="w-3.5 h-3.5 rounded-full bg-yellow-500"></div>
                                <div class="w-3.5 h-3.5 rounded-full bg-green-500"></div>
                            </div>
                            <div class="space-y-3">
                                <div class="text-slate-400"><span class="text-emerald-400">root@refugio-seguro</span>:~$ start_transaction --secure</div>
                                <div class="text-slate-300">&gt; Iniciando pasarela cifrada... [OK]</div>
                                <div class="text-slate-300">&gt; Verificando protocolo SSL (PCI-DSS)... [OK]</div>
                                <div class="text-slate-300">&gt; Procesando token: tok_1NiK92x... [OK]</div>
                                <div class="text-slate-400 mt-4"><span class="text-emerald-400">root@refugio-seguro</span>:~$ generate_ledger_hash</div>
                                <div class="text-slate-300">&gt; Creando ID inmutable de trazabilidad...</div>
                                <div class="text-blue-400 font-bold bg-blue-500/10 p-2 rounded mt-2">&gt; HASH: 0x8f4b2a9e2d31...e71c</div>
                                <div class="text-white font-bold mt-6 flex items-center gap-2">
                                    <i data-lucide="shield-check" class="w-[18px] h-[18px] text-emerald-500"></i> Transacción asegurada y publicada en el portal de transparencia.
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-slate-900 text-slate-400 py-16 border-t border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid md:grid-cols-4 gap-10">
            <div class="md:col-span-2">
                <div class="flex items-center gap-2 mb-6">
                    <i data-lucide="heart" class="w-6 h-6 text-blue-500"></i>
                    <span class="font-extrabold text-2xl text-white">Refugio<span class="text-blue-500">Seguro</span></span>
                </div>
                <p class="text-slate-400 leading-relaxed max-w-sm">
                    Organización sin fines de lucro registrada. Construyendo un puente directo de ayuda con tecnología, transparencia y empatía total.
                </p>
            </div>
            <div>
                <h4 class="text-white font-bold mb-6 uppercase tracking-wider text-sm">Transparencia</h4>
                <ul class="space-y-3 text-slate-400">
                    <li><a href="#" class="hover:text-white transition-colors">Aviso de Privacidad</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Garantía Cero Desvío</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Reportes Auditados 2023</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Estatutos de la ONG</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-white font-bold mb-6 uppercase tracking-wider text-sm">Contacto</h4>
                <ul class="space-y-3 text-slate-400">
                    <li>hola@refugioseguro.org</li>
                    <li>+52 (55) 1234-5678</li>
                    <li>Av. Solidaridad 123, Piso 4<br>Ciudad de México</li>
                </ul>
            </div>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-16 pt-8 border-t border-slate-800 text-sm flex flex-col md:flex-row justify-between items-center gap-4">
            <span>© <span id="currentYear"></span> Refugio Seguro AC. Todos los derechos reservados.</span>
            <span class="flex items-center gap-1">Hecho con <i data-lucide="heart" class="w-3.5 h-3.5 text-red-500"></i> para un mundo mejor.</span>
        </div>
    </footer>

    <!-- Donate Modal Overlay -->
    <div id="donateModal" class="hidden fixed inset-0 z-50 items-center justify-center p-4 bg-slate-900/70 backdrop-blur-md">
        <div class="bg-white rounded-3xl w-full max-w-lg overflow-hidden shadow-2xl animate-zoom-in">
            <!-- Header -->
            <div class="bg-slate-50 px-8 py-6 border-b border-slate-200 flex justify-between items-center">
                <div>
                    <h3 class="text-2xl font-black text-slate-900 flex items-center gap-2">
                        Apartado de Pago Segura
                    </h3>
                    <span class="text-emerald-600 text-sm font-bold flex items-center gap-1 mt-1">
                        <i data-lucide="lock" class="w-3.5 h-3.5"></i> Conexión Encriptada SSL
                    </span>
                </div>
                <button onclick="closeDonateModal()" class="text-slate-400 hover:text-slate-800 bg-slate-200 hover:bg-slate-300 w-8 h-8 rounded-full flex items-center justify-center transition-colors text-xl leading-none">&times;</button>
            </div>

            <!-- Form -->
            <form id="donationForm" class="p-8">
                <div class="mb-6">
                    <label class="block text-sm font-bold text-slate-700 mb-3 uppercase tracking-wide">Monto a Donar (MXN)</label>
                    <div class="grid grid-cols-4 gap-3 mb-4" id="presetAmounts">
                        <button type="button" onclick="selectAmount(200, this)" class="preset-btn py-3 px-2 rounded-xl border-2 font-black transition-all border-slate-200 text-slate-500 hover:border-blue-300 hover:bg-slate-50">$200</button>
                        <button type="button" onclick="selectAmount(500, this)" class="preset-btn py-3 px-2 rounded-xl border-2 font-black transition-all bg-blue-50 border-blue-600 text-blue-700">$500</button>
                        <button type="button" onclick="selectAmount(1000, this)" class="preset-btn py-3 px-2 rounded-xl border-2 font-black transition-all border-slate-200 text-slate-500 hover:border-blue-300 hover:bg-slate-50">$1000</button>
                        <button type="button" onclick="selectAmount(2000, this)" class="preset-btn py-3 px-2 rounded-xl border-2 font-black transition-all border-slate-200 text-slate-500 hover:border-blue-300 hover:bg-slate-50">$2000</button>
                    </div>
                    <div class="relative">
                        <span class="absolute left-4 top-1/2 -translate-y-1/2 text-slate-500 font-bold">$</span>
                        <input type="number" id="customAmountInput" oninput="handleCustomAmount()" placeholder="Ingresar otro monto" class="w-full pl-10 pr-4 py-3 border-2 border-slate-200 rounded-xl focus:ring-0 focus:border-blue-500 outline-none transition-colors font-bold text-slate-800">
                    </div>
                </div>

                <div class="mb-6">
                    <label class="block text-sm font-bold text-slate-700 mb-3 uppercase tracking-wide">¿A dónde enviamos tu donación?</label>
                    <select id="purposeSelect" class="w-full px-4 py-3 border-2 border-slate-200 rounded-xl focus:ring-0 focus:border-blue-500 outline-none font-bold text-slate-700 appearance-none bg-slate-50">
                        <option value="General">Fondo General (Donde más urge)</option>
                        <option value="Alimentos">Exclusivo: Refugio y Comida</option>
                        <option value="Salud">Exclusivo: Atención Médica</option>
                    </select>
                </div>

                <div class="space-y-5 mb-8">
                    <div>
                        <label class="block text-sm font-bold text-slate-700 mb-2">Nombre del Donante</label>
                        <input id="donorNameInput" type="text" placeholder="Ej. Juan Pérez (O dejar en blanco para Anónimo)" class="w-full px-4 py-3 border-2 border-slate-200 rounded-xl focus:ring-0 focus:border-blue-500 outline-none">
                    </div>
                    
                    <!-- Tarjeta Fake -->
                    <div class="p-5 bg-slate-50 border-2 border-slate-200 rounded-2xl relative">
                        <div class="flex justify-between items-center mb-4">
                            <span class="text-sm font-black text-slate-800 flex items-center gap-2">
                                <i data-lucide="credit-card" class="w-[18px] h-[18px] text-blue-600"></i> Tarjeta de Crédito/Débito
                            </span>
                            <div class="flex gap-1">
                                <div class="w-8 h-5 bg-slate-200 rounded"></div>
                                <div class="w-8 h-5 bg-slate-200 rounded"></div>
                            </div>
                        </div>
                        <input required type="text" placeholder="0000 0000 0000 0000" class="w-full px-4 py-3 mb-3 border border-slate-300 rounded-xl outline-none font-mono tracking-widest text-slate-700 focus:border-blue-500">
                        <div class="flex gap-3">
                            <input required type="text" placeholder="MM/AA" class="w-1/2 px-4 py-3 border border-slate-300 rounded-xl outline-none text-center focus:border-blue-500">
                            <input required type="text" placeholder="CVC" class="w-1/2 px-4 py-3 border border-slate-300 rounded-xl outline-none text-center focus:border-blue-500">
                        </div>
                    </div>
                </div>

                <button type="submit" id="submitBtn" class="w-full bg-blue-600 hover:bg-blue-700 disabled:bg-blue-400 text-white font-black py-4 px-6 rounded-2xl transition-all flex items-center justify-center gap-2 text-lg shadow-xl shadow-blue-500/30">
                    <span id="btnText">Completar Donación de $500 MXN</span>
                    <span id="loadingSpinner" class="hidden items-center gap-3">
                        <svg class="animate-spin h-6 w-6 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                            <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                            <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                        </svg>
                        Procesando pago seguro...
                    </span>
                </button>
                
                <div class="mt-6 flex flex-col items-center justify-center text-xs text-slate-500 font-medium">
                    <span class="flex items-center gap-1 mb-1">
                        <i data-lucide="shield-check" class="w-3.5 h-3.5 text-emerald-500"></i> Transacción procesada de forma segura
                    </span>
                    <p>Al donar, aceptas nuestra política de transparencia total.</p>
                </div>
            </form>
        </div>
    </div>

    <!-- Ticket Modal Overlay -->
    <div id="ticketModal" class="hidden fixed inset-0 z-50 items-center justify-center p-4 bg-slate-900/80 backdrop-blur-md">
        <div class="bg-white rounded-3xl w-full max-w-md overflow-hidden shadow-2xl animate-slide-up">
            
            <!-- Header Ticket -->
            <div class="bg-emerald-500 p-8 text-center text-white relative">
                <div class="mx-auto w-20 h-20 bg-white rounded-full flex items-center justify-center mb-4 shadow-xl">
                    <i data-lucide="check-circle" class="w-10 h-10 text-emerald-500"></i>
                </div>
                <h2 class="text-3xl font-black mb-2">¡Pago Exitoso!</h2>
                <p class="text-emerald-100 font-medium">Tu aporte ya está salvando vidas.</p>
                
                <!-- Ticket cut border -->
                <div class="absolute -bottom-3 left-0 w-full overflow-hidden flex justify-between px-2">
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                    <div class="w-4 h-4 bg-white rounded-full translate-y-2"></div>
                </div>
            </div>

            <!-- Body Ticket -->
            <div class="p-8 pt-10 bg-white">
                <div class="text-center mb-8">
                    <span class="block text-slate-400 text-sm mb-1 font-bold uppercase tracking-wider">Monto Total Donado</span>
                    <span class="text-5xl font-black text-slate-800">$<span id="ticketAmount"></span> <span class="text-xl text-slate-400 font-bold">MXN</span></span>
                </div>

                <div class="space-y-4 border-y-2 border-dashed border-slate-200 py-6 mb-8">
                    <div class="flex justify-between items-center">
                        <span class="text-slate-500 text-sm font-bold">Donante</span>
                        <span id="ticketDonor" class="font-black text-slate-800"></span>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-slate-500 text-sm font-bold">Destino de Fondos</span>
                        <span id="ticketPurpose" class="font-bold text-blue-600 bg-blue-50 px-3 py-1 rounded-full text-sm"></span>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-slate-500 text-sm font-bold">Fecha y Hora</span>
                        <span id="ticketDate" class="font-bold text-slate-800 text-sm"></span>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-slate-500 text-sm font-bold">ID de Seguimiento</span>
                        <span id="ticketId" class="font-mono bg-slate-100 px-2 py-1 rounded text-sm text-slate-700 font-bold"></span>
                    </div>
                </div>

                <div class="mb-8 bg-slate-50 p-4 rounded-xl border border-slate-200">
                    <span class="block text-slate-500 text-xs mb-2 text-center font-bold">HASH DE TRAZABILIDAD PÚBLICA (LEDGER)</span>
                    <div id="ticketHash" class="text-center break-all font-mono text-xs text-slate-400">
                    </div>
                </div>

                <div class="flex gap-4">
                    <button onclick="closeTicketModal()" class="w-1/3 py-3 rounded-2xl border-2 border-slate-200 text-slate-600 font-bold hover:bg-slate-50 transition-colors">
                        Cerrar
                    </button>
                    <button onclick="downloadReceipt()" class="w-2/3 py-3 rounded-2xl bg-blue-600 text-white font-bold hover:bg-blue-700 transition-colors flex items-center justify-center gap-2 shadow-lg shadow-blue-500/30">
                        <i data-lucide="download" class="w-[18px] h-[18px]"></i> Descargar Recibo
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Lógica JavaScript -->
    <script>
        // Inicializar Iconos Lucide
        lucide.createIcons();
        
        // Poner año actual en el footer
        document.getElementById('currentYear').textContent = new Date().getFullYear();

        // Variables de Estado
        let selectedAmount = 500;
        let isProcessing = false;

        // Elementos DOM
        const donateModal = document.getElementById('donateModal');
        const ticketModal = document.getElementById('ticketModal');
        const customAmountInput = document.getElementById('customAmountInput');
        const presetBtns = document.querySelectorAll('.preset-btn');
        const btnText = document.getElementById('btnText');
        const loadingSpinner = document.getElementById('loadingSpinner');
        const submitBtn = document.getElementById('submitBtn');
        const donationForm = document.getElementById('donationForm');

        // Lógica de Modales
        function openDonateModal() {
            donateModal.classList.remove('hidden');
            donateModal.classList.add('flex');
            document.body.style.overflow = 'hidden';
        }

        function closeDonateModal() {
            donateModal.classList.add('hidden');
            donateModal.classList.remove('flex');
            document.body.style.overflow = '';
        }

        function openTicketModal() {
            ticketModal.classList.remove('hidden');
            ticketModal.classList.add('flex');
            document.body.style.overflow = 'hidden';
        }

        function closeTicketModal() {
            ticketModal.classList.add('hidden');
            ticketModal.classList.remove('flex');
            document.body.style.overflow = '';
        }

        // Seleccionar monto
        function selectAmount(amount, btnElement) {
            selectedAmount = amount;
            customAmountInput.value = ''; // Limpiar campo personalizado
            updateAmountUI(btnElement);
        }

        function handleCustomAmount() {
            const val = customAmountInput.value;
            if (val) {
                selectedAmount = parseFloat(val);
                updateAmountUI(null); // Quitar selección de los predefinidos
            } else {
                selectAmount(500, presetBtns[1]); // Volver al default
            }
        }

        function updateAmountUI(activeBtn) {
            // Resetear todos los botones
            presetBtns.forEach(btn => {
                btn.classList.remove('bg-blue-50', 'border-blue-600', 'text-blue-700');
                btn.classList.add('border-slate-200', 'text-slate-500');
            });

            // Activar el clickeado
            if (activeBtn) {
                activeBtn.classList.remove('border-slate-200', 'text-slate-500');
                activeBtn.classList.add('bg-blue-50', 'border-blue-600', 'text-blue-700');
            }

            // Actualizar texto del botón principal
            if(selectedAmount > 0) {
                btnText.textContent = `Completar Donación de $${selectedAmount} MXN`;
                submitBtn.disabled = false;
            } else {
                btnText.textContent = `Ingresa un monto válido`;
                submitBtn.disabled = true;
            }
        }

        // Manejar el submit del formulario
        donationForm.addEventListener('submit', function(e) {
            e.preventDefault();
            if(isProcessing) return;

            // Recolectar datos
            const finalAmount = selectedAmount;
            const purpose = document.getElementById('purposeSelect').value;
            const donorName = document.getElementById('donorNameInput').value || 'Anónimo';

            // Iniciar procesamiento visual
            isProcessing = true;
            submitBtn.disabled = true;
            btnText.classList.add('hidden');
            loadingSpinner.classList.remove('hidden');
            loadingSpinner.classList.add('flex');

            // Simular petición al servidor (2.5 seg)
            setTimeout(() => {
                // Generar datos falsos de ticket
                const ticketId = `TXN-${Math.floor(100000 + Math.random() * 900000)}`;
                const hashArray = Array.from({length: 40}, () => Math.floor(Math.random()*16).toString(16));
                const hash = `0x${hashArray.join('')}`;
                const date = new Date().toLocaleString('es-MX');

                // Llenar datos en el Modal del Ticket
                document.getElementById('ticketAmount').textContent = finalAmount;
                document.getElementById('ticketDonor').textContent = donorName;
                document.getElementById('ticketPurpose').textContent = purpose;
                document.getElementById('ticketDate').textContent = date;
                document.getElementById('ticketId').textContent = ticketId;
                document.getElementById('ticketHash').textContent = hash;

                // Restaurar estado del botón
                isProcessing = false;
                submitBtn.disabled = false;
                btnText.classList.remove('hidden');
                loadingSpinner.classList.add('hidden');
                loadingSpinner.classList.remove('flex');
                
                // Limpiar formulario y monto
                donationForm.reset();
                selectAmount(500, presetBtns[1]);

                // Cambiar de modales
                closeDonateModal();
                openTicketModal();
            }, 2500);
        });

        // Simular descarga de recibo
        function downloadReceipt() {
            const ticketId = document.getElementById('ticketId').textContent;
            alert(`Simulando descarga de: Recibo_Fiscal_${ticketId}.pdf`);
        }
    </script>
</body>
</html>
