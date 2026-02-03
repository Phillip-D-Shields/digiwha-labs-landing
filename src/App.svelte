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
    },
    {
      name: "BREATHE",
      tagline: "Reset Your System",
      icon: "🫁",
      color: "#c792e9",
      stats: { FLOW: 99, PROD: 30, ZEN: 95 },
      features: ["Box Breathing", "Vagal Nerve Reset", "Heart Rate Sync"],
      url: "https://breathe.digiwha-labs.com",
    },
  ];

  const comingSoon = [
    {
      name: "HYDRATE",
      tagline: "Fuel the Biological Machine",
      icon: "💧",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["Fluid Tracking", "Electrolyte Alerts"]
    },
    {
      name: "DREAM",
      tagline: "Data-Mine Your Subconscious",
      icon: "🌙",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["REM Cycles", "Lucid Triggers"]
    },
    {
      name: "STRETCH",
      tagline: "Recalibrate Physical Form",
      icon: "🤸",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["Desk Yoga", "Postures"]
    },
    {
      name: "DECIDER",
      tagline: "High Stakes Choice Support",
      icon: "🧠",
      stats: { FLOW: "??", PROD: "??", ZEN: "??" },
      features: ["Chaos Analysis", "Outcome Simulation"]
    }
  ];
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

    <div class="flex flex-col items-center">
      <h1
        class="text-5xl font-bold tracking-tighter uppercase mb-2 font-center"
        style="text-shadow: 4px 4px #ff7d5d;"
      >
        Digiwha Labs
      </h1>
      <div class="flex items-center gap-4">
        <span class="h-[2px] w-12 bg-[#c792e9]"></span>
        <p class="text-[#c792e9] uppercase tracking-widest text-md italic">
          Bio-Digital Enhancement Suite
        </p>
        <span class="h-[2px] w-12 bg-[#c792e9]"></span>
      </div>
      <p class="text-sm uppercase tracking-tighter text-center">
        Now installable as a PWA!<br />Slap it on your device for offline access<br
        />Free forever because we love you
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

        <div class="card-body p-5 gap-4">
          <div class="flex flex-col">
            <p class="text-[10px] uppercase text-[#c792e9] font-bold">
              // Mission Statement
            </p>
            <p class="text-xs uppercase leading-tight">{app.tagline}</p>
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

    <!-- coming soon -->
    {#each comingSoon as app}
      <div
        class="card w-80 bg-[#1d212a] border-4 border-gray-600 rounded-none opacity-60 grayscale relative overflow-hidden group"
      >
        <!-- <div
          class="absolute inset-0 z-10 flex items-center justify-center bg-[#242933]/40 backdrop-blur-[1px]"
        >
          <div
            class="bg-[#ff7d5d] text-[#242933] font-black px-4 py-1 rotate-12 border-2 border-[#242933] shadow-[4px_4px_0px_0px_#242933]"
          >
            COMING SOON
          </div>
        </div> -->

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
  </footer>
</div>

<style>
  :global(body) {
    background-color: #242933;
    /* This makes the whole UI feel more like an old screen */
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
