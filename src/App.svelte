<script>
  import logo from "./assets/logo.png";
  
  const apps = [
    {
      name: "FOCUS",
      tagline: "Time is a Resource",
      icon: "⏳",
      color: "#9fe88d",
      stats: { FLOW: 85, PROD: 92, ZEN: 40 },
      features: ["Pomodoro Timer", "Task Ghosting", "Deep Work Mode"],
      url: "https://focus.digiwha-labs.com",
      // ADDED: Description field
      desc: "A dedicated Pomodoro timer that stores your daily session count locally in your browser cache. It auto-resets the counter every 24 hours. No cloud, no distractions."
    },
    {
      name: "BREATHE",
      tagline: "Reset Your System",
      icon: "🫁",
      color: "#c792e9",
      stats: { FLOW: 99, PROD: 30, ZEN: 95 },
      features: ["Box Breathing", "Vagal Nerve Reset", "Heart Rate Sync"],
      url: "https://breathe.digiwha-labs.com",
      // ADDED: Description field
      desc: "An interactive breathing pacer utilizing the 4-4-4-4 'Box Breathing' technique. Uses visual cues to help down-regulate your nervous system and reduce cortisol."
    },
    {
      name: "DECIDE",
      tagline: "Eliminate Analysis Paralysis", 
      icon: "🎰", 
      color: "#ffadad", 
      stats: { FLOW: 60, PROD: 95, ZEN: 80 }, 
      features: ["Visual Randomizer", "Outcome Simulation", "Bias Removal"],
      url: "https://decide.digiwha-labs.com",
      // ADDED: Description field
      desc: "A decision-making engine. Input your dilemma options, and the algorithm selects the outcome, effectively outsourcing your executive function to remove decision fatigue."
    },
  ];

  const comingSoon = [
    {
      name: "HYDRATE",
      tagline: "Fuel the Biological Machine",
      icon: "💧",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["Fluid Tracking", "Electrolyte Alerts"],
    },
    {
      name: "DREAM",
      tagline: "Data-Mine Your Subconscious",
      icon: "🌙",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["REM Cycles", "Lucid Triggers"],
    },
    {
      name: "STRETCH",
      tagline: "Recalibrate Physical Form",
      icon: "🤸",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["Desk Yoga", "Postures"],
    },
  ];

  let showInfo = false;
  const toggleInfo = () => showInfo = !showInfo;
</script>

<div
  class="min-h-screen bg-[#242933] text-[#9fe88d] font-mono p-8 relative overflow-hidden"
>
  <header class="flex justify-center items-center gap-4 mb-16">
    <div
      class="hidden md:block w-48 h-48 mb-4 border-4 border-[#9fe88d] shadow-[6px_6px_0px_0px_#c792e9] bg-[#1d212a] overflow-hidden flex items-center justify-center"
    >
      <img src={logo} alt="Digiwha Labs" class="w-full h-full object-cover" />
    </div>

    <div class="flex flex-col items-center text-center max-w-lg">
      <h1
        class="text-5xl font-bold tracking-tighter uppercase mb-2"
        style="text-shadow: 4px 4px #ff7d5d;"
      >
        Digiwha Labs
      </h1>
      <div class="flex items-center gap-4">
        <span class="h-[2px] w-6 bg-[#c792e9]"></span>
        <p class="text-[#c792e9] uppercase tracking-widest text-md italic">
          Bio-Digital Enhancement PWA Suite
        </p>
        <span class="h-[2px] w-6 bg-[#c792e9]"></span>
      </div>
      <p class="text-sm uppercase tracking-tighter text-center">
        Each installable as a PWA!<br />Slap it on your device<br
        />Free forever because we love you<br /> 
      </p>
    </div>
  </header>

  <div class="flex flex-wrap justify-center gap-12 max-w-6xl mx-auto">
    {#each apps as app}
      <div
        class="card w-80 bg-[#1d212a] border-4 border-[#9fe88d] rounded-none shadow-[8px_8px_0px_0px_#ff7d5d] hover:translate-x-[-2px] hover:translate-y-[-2px] hover:shadow-[12px_12px_0px_0px_#c792e9] transition-all group"
      >
        <div
          class="p-4 border-b-4 border-[#9fe88d] flex justify-between items-center bg-[#242933]"
        >
          <span
            class="font-bold uppercase italic text-lg group-hover:text-[#ff7d5d]"
            >{app.name}</span
          >
          <span class="text-[10px] bg-[#9fe88d] text-[#242933] px-1 font-bold"
            >READY</span
          >
        </div>

        <figure class="px-10 pt-10 pb-5 bg-neutral-900/50">
          <div class="text-7xl filter drop-shadow-[4px_4px_0px_#ff7d5d]">
            {app.icon}
          </div>
        </figure>

        <div class="card-body p-5 gap-4 relative">
          <div class="flex justify-between items-center">
            <div class="flex flex-col">
              <p class="text-[10px] uppercase text-[#c792e9] font-bold">
                // Mission Statement
              </p>
              <p class="text-xs uppercase leading-tight">{app.tagline}</p>
            </div>

            <div class="group/info relative ml-2">
              <button class="text-[10px] font-bold text-[#ff7d5d] border border-[#ff7d5d] p-1 hover:bg-[#ff7d5d] hover:text-[#242933] cursor-help transition-colors">
                [?] INFO
              </button>

              <div class="absolute bottom-6 right-0 w-64 p-3 bg-[#1d212a] border-2 border-[#ff7d5d] shadow-[4px_4px_0px_0px_#242933] z-50 opacity-0 invisible group-hover/info:opacity-100 group-hover/info:visible transition-all duration-200 pointer-events-none group-hover/info:pointer-events-auto">
                <p class="text-[10px] text-[#ff7d5d] font-bold mb-2 uppercase border-b border-[#ff7d5d] inline-block">
                  :: SYSTEM_DESC ::
                </p>
                <p class="text-xs text-gray-300 leading-snug">
                  {app.desc}
                </p>
              </div>
            </div>
          </div>

          <div class="bg-[#242933] p-3 border-2 border-[#c792e9] relative">
            <span
              class="absolute -top-3 left-2 bg-[#242933] px-2 text-[10px] text-[#c792e9]"
              >CORE_STATS</span
            >
            {#each Object.entries(app.stats) as [label, value]}
              <div class="flex justify-between items-center mb-1">
                <span class="text-[10px]">{label}</span>
                <div class="w-28 bg-gray-800 h-3 border border-[#9fe88d]">
                  <div
                    class="bg-[#ff7d5d] h-full"
                    style="width: {value}%"
                  ></div>
                </div>
              </div>
            {/each}
          </div>

          <div class="card-actions mt-4">
            <a
              href={app.url}
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-block bg-[#9fe88d] hover:bg-[#ff7d5d] text-[#242933] rounded-none border-none font-black text-lg shadow-[4px_4px_0px_0px_#c792e9] active:shadow-none active:translate-x-[4px] active:translate-y-[4px]"
            >
              INITIALIZE
            </a>
          </div>
        </div>
      </div>
    {/each}

    {#each comingSoon as app}
      <div
        class="card w-80 bg-[#1d212a] border-4 border-gray-600 rounded-none opacity-60 grayscale relative overflow-hidden group"
      >
        <div
          class="p-4 border-b-4 border-gray-600 flex justify-between items-center bg-[#242933]"
        >
          <span class="font-bold uppercase italic text-lg">{app.name}</span>
          <span
            class="text-[10px] bg-gray-600 text-[#242933] px-1 font-bold italic"
            >ENCRYPTED</span
          >
        </div>

        <figure class="px-10 pt-10 pb-5">
          <div class="text-7xl opacity-30">{app.icon}</div>
        </figure>

        <div class="card-body p-5 gap-4">
          <div>
            <p class="text-[10px] uppercase text-gray-500 font-bold">
              // Status: Pending
            </p>
            <p class="text-xs uppercase leading-tight">{app.tagline}</p>
          </div>

          <div class="bg-[#242933] p-3 border-2 border-gray-700 opacity-50">
            {#each Object.entries(app.stats) as [label, value]}
              <div class="flex justify-between items-center mb-1 text-gray-500">
                <span class="text-[10px]">{label}</span>
                <span class="text-[10px] font-mono tracking-widest"
                  >ERROR_404</span
                >
              </div>
            {/each}
          </div>

          <div class="card-actions mt-4">
            <button
              disabled
              class="btn btn-block bg-gray-700 text-gray-400 rounded-none border-none"
            >
              COMING SOON
            </button>
          </div>
        </div>
      </div>
    {/each}
  </div>

  <footer
    class="mt-20 text-center text-[10px] text-gray-500 uppercase tracking-widest"
  >
    © 2026 Digiwha Labs // Neural Link Established
    <br />
    <a
      href="https://www.buymeacoffee.com/phill_shields"
      target="_blank"
      rel="noreferrer"
      class="btn btn-ghost btn-sm mt-4 opacity-40 hover:opacity-100 transition-all"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-3 w-3 text-error"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
        />
      </svg>
      Buy Me a Coffee
    </a>
  </footer>
  <button 
  on:click={toggleInfo}
  class="fixed bottom-8 right-8 z-50 bg-[#c792e9] text-[#242933] font-black p-4 border-4 border-[#242933] shadow-[4px_4px_0px_0px_#9fe88d] hover:translate-x-[-2px] hover:translate-y-[-2px] hover:shadow-[6px_6px_0px_0px_#9fe88d] transition-all"
>
  [?] SYSTEM_README
</button>

{#if showInfo}
  <div class="fixed inset-0 z-[100] flex items-center justify-center p-4 bg-[#242933]/90 backdrop-blur-sm">
    <div class="bg-[#1d212a] border-4 border-[#9fe88d] p-8 max-w-lg w-full shadow-[12px_12px_0px_0px_#ff7d5d] relative">
      <button on:click={toggleInfo} class="absolute top-2 right-2 text-[#ff7d5d] hover:bg-[#ff7d5d] hover:text-[#242933] px-2 border-2 border-[#ff7d5d]">X</button>
      
      <h2 class="text-2xl font-black text-[#9fe88d] uppercase tracking-tighter italic">// WHAT IS A PWA?</h2>
      <p class="text-xs uppercase tracking-wider mb-4 text-[#ff7d5d]">// It's a Progressive Web App!</p>
      
      <div class="space-y-6 text-sm">
        <section>
          <h3 class="text-[#c792e9] font-bold underline mb-1">LOCAL_HOSTED_DATA</h3>
          <p>These apps are "Progressive Web Apps." Your data never touches a cloud. It lives in your browser's local cache. No accounts, no tracking, no leaks.</p>
        </section>

        <section>
          <h3 class="text-[#c792e9] font-bold underline mb-1">HARDWARE_INSTALL</h3>
          <p>Each PWA has an "Install App" button that will trigger the install protocol or present instructions on how to install on your device. This bypasses the corporate app stores and sits directly on your OS.</p>
        </section>

        <section>
          <h3 class="text-[#c792e9] font-bold underline mb-1">OFFLINE_READY</h3>
          <p>Once initialized, these tools work in deep-space or underground bunkers. No signal required for core functionality.</p>
        </section>
      </div>

      <button 
        on:click={toggleInfo}
        class="mt-8 w-full bg-[#9fe88d] text-[#242933] font-bold py-2 border-2 border-[#242933] shadow-[4px_4px_0px_0px_#c792e9]"
      >
        ACKNOWLEDGE & CLOSE
      </button>
    </div>
  </div>
{/if}
</div>

<style>
  :global(body) {
    background-color: #242933;
    background-image: linear-gradient(
        rgba(18, 16, 16, 0) 50%,
        rgba(0, 0, 0, 0.1) 50%
      ),
      linear-gradient(
        90deg,
        rgba(255, 0, 0, 0.03),
        rgba(0, 255, 0, 0.01),
        rgba(0, 0, 255, 0.03)
      );
    background-size:
      100% 4px,
      3px 100%;
  }
</style>