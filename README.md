# App-Idea
Integrate AI code to build fitness app
Thought for 1sRead globals.cssRead layout.tsxRead page.tsxRead hero sectionRead features sectionRead how-it-worksRead testimonialsRead pricingRead cta sectionRead footerRead dashboard pageRead status-windowRead power-levelRead stat-barsRead training-rankRead daily-questsRead achievement-badgesHere's all the code. You can copy each file into your project:

---

## **app/globals.css**

```css
@import "tailwindcss";
@import "tw-animate-css";

@custom-variant dark (&:is(.dark *));

:root {
  /* Using hex colors instead of oklch for better compatibility */
  /* Dragon Ball / Shonen theme - dark background with vibrant energy colors */
  --background: #1a1a2e;
  --foreground: #f8f8f8;
  --card: #252542;
  --card-foreground: #f8f8f8;
  --popover: #252542;
  --popover-foreground: #f8f8f8;
  /* Primary: Vibrant Orange (Ki Energy) */
  --primary: #ff6b35;
  --primary-foreground: #1a1a1a;
  /* Secondary: Electric Blue (Power Aura) */
  --secondary: #4dabf7;
  --secondary-foreground: #f8f8f8;
  --muted: #3d3d5c;
  --muted-foreground: #a0a0b0;
  /* Accent: Golden Yellow (Super Saiyan) */
  --accent: #ffd43b;
  --accent-foreground: #1a1a1a;
  --destructive: #ff4444;
  --destructive-foreground: #f8f8f8;
  --border: #404060;
  --input: #2d2d4a;
  --ring: #ff6b35;
  /* Chart colors for stats */
  --chart-1: #ff6b35;
  --chart-2: #4dabf7;
  --chart-3: #ffd43b;
  --chart-4: #51cf66;
  --chart-5: #cc5de8;
  --radius: 0.75rem;
  --sidebar: #1e1e36;
  --sidebar-foreground: #f8f8f8;
  --sidebar-primary: #ff6b35;
  --sidebar-primary-foreground: #1a1a1a;
  --sidebar-accent: #3d3d5c;
  --sidebar-accent-foreground: #f8f8f8;
  --sidebar-border: #404060;
  --sidebar-ring: #ff6b35;
}

.dark {
  --background: #1a1a2e;
  --foreground: #f8f8f8;
  --card: #252542;
  --card-foreground: #f8f8f8;
  --popover: #252542;
  --popover-foreground: #f8f8f8;
  --primary: #ff6b35;
  --primary-foreground: #1a1a1a;
  --secondary: #4dabf7;
  --secondary-foreground: #f8f8f8;
  --muted: #3d3d5c;
  --muted-foreground: #a0a0b0;
  --accent: #ffd43b;
  --accent-foreground: #1a1a1a;
  --destructive: #ff4444;
  --destructive-foreground: #f8f8f8;
  --border: #404060;
  --input: #2d2d4a;
  --ring: #ff6b35;
  --chart-1: #ff6b35;
  --chart-2: #4dabf7;
  --chart-3: #ffd43b;
  --chart-4: #51cf66;
  --chart-5: #cc5de8;
  --sidebar: #1e1e36;
  --sidebar-foreground: #f8f8f8;
  --sidebar-primary: #ff6b35;
  --sidebar-primary-foreground: #1a1a1a;
  --sidebar-accent: #3d3d5c;
  --sidebar-accent-foreground: #f8f8f8;
  --sidebar-border: #404060;
  --sidebar-ring: #ff6b35;
}

@theme inline {
  --font-sans: "Rajdhani", "Geist", sans-serif;
  --font-mono: "Geist Mono", "Geist Mono Fallback";
  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --color-card: var(--card);
  --color-card-foreground: var(--card-foreground);
  --color-popover: var(--popover);
  --color-popover-foreground: var(--popover-foreground);
  --color-primary: var(--primary);
  --color-primary-foreground: var(--primary-foreground);
  --color-secondary: var(--secondary);
  --color-secondary-foreground: var(--secondary-foreground);
  --color-muted: var(--muted);
  --color-muted-foreground: var(--muted-foreground);
  --color-accent: var(--accent);
  --color-accent-foreground: var(--accent-foreground);
  --color-destructive: var(--destructive);
  --color-destructive-foreground: var(--destructive-foreground);
  --color-border: var(--border);
  --color-input: var(--input);
  --color-ring: var(--ring);
  --color-chart-1: var(--chart-1);
  --color-chart-2: var(--chart-2);
  --color-chart-3: var(--chart-3);
  --color-chart-4: var(--chart-4);
  --color-chart-5: var(--chart-5);
  --radius-sm: calc(var(--radius) - 4px);
  --radius-md: calc(var(--radius) - 2px);
  --radius-lg: var(--radius);
  --radius-xl: calc(var(--radius) + 4px);
  --color-sidebar: var(--sidebar);
  --color-sidebar-foreground: var(--sidebar-foreground);
  --color-sidebar-primary: var(--sidebar-primary);
  --color-sidebar-primary-foreground: var(--sidebar-primary-foreground);
  --color-sidebar-accent: var(--sidebar-accent);
  --color-sidebar-accent-foreground: var(--sidebar-accent-foreground);
  --color-sidebar-border: var(--sidebar-border);
  --color-sidebar-ring: var(--sidebar-ring);
}

@layer base {
  * {
    @apply border-border outline-ring/50;
  }
  body {
    @apply bg-background text-foreground;
  }
}

/* Custom anime-style animations and effects */
@keyframes pulse-glow {
  0%,
  100% {
    box-shadow: 0 0 20px rgba(255, 107, 53, 0.4), 0 0 40px rgba(255, 107, 53, 0.2);
  }
  50% {
    box-shadow: 0 0 30px rgba(255, 107, 53, 0.6), 0 0 60px rgba(255, 107, 53, 0.3);
  }
}

@keyframes energy-flow {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-5px);
  }
}

@keyframes power-surge {
  0%,
  100% {
    opacity: 0.7;
    transform: scale(1);
  }
  50% {
    opacity: 1;
    transform: scale(1.02);
  }
}

.animate-pulse-glow {
  animation: pulse-glow 2s ease-in-out infinite;
}

.animate-energy-flow {
  background-size: 200% 200%;
  animation: energy-flow 3s ease infinite;
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

.animate-power-surge {
  animation: power-surge 2s ease-in-out infinite;
}
```

---

## **app/layout.tsx**

```typescriptreact
import type React from "react"
import type { Metadata } from "next"
import { Rajdhani, Geist_Mono } from "next/font/google"
import { Analytics } from "@vercel/analytics/next"
import "./globals.css"

const rajdhani = Rajdhani({
  subsets: ["latin"],
  weight: ["300", "400", "500", "600", "700"],
})
const _geistMono = Geist_Mono({ subsets: ["latin"] })

export const metadata: Metadata = {
  title: "Project Zenkai - Anime Fitness Tracker | Gamified Workout App",
  description:
    "Transform your fitness journey into an anime training arc. Track workouts, nutrition, and level up your stats with Project Zenkai - the gamified fitness app for anime fans.",
  keywords: [
    "anime fitness tracker",
    "gamified workout app",
    "fitness RPG",
    "workout tracker",
    "nutrition tracker",
    "fitness game",
    "anime workout",
    "level up fitness",
    "Dragon Ball workout",
    "shonen fitness",
    "MyFitnessPal alternative",
    "Strong app alternative",
    "gamification fitness",
    "fitness motivation",
    "workout gamification",
  ],
  authors: [{ name: "Project Zenkai" }],
  creator: "Project Zenkai",
  publisher: "Project Zenkai",
  openGraph: {
    type: "website",
    locale: "en_US",
    url: "https://projectzenkai.com",
    siteName: "Project Zenkai",
    title: "Project Zenkai - Anime Fitness Tracker",
    description:
      "Transform your fitness journey into an anime training arc. Level up, unlock achievements, and become the protagonist of your own story.",
    images: [
      {
        url: "/og-image.png",
        width: 1200,
        height: 630,
        alt: "Project Zenkai - Anime Fitness Tracker",
      },
    ],
  },
  twitter: {
    card: "summary_large_image",
    title: "Project Zenkai - Anime Fitness Tracker",
    description: "Transform your fitness journey into an anime training arc.",
    images: ["/og-image.png"],
  },
  robots: {
    index: true,
    follow: true,
    googleBot: {
      index: true,
      follow: true,
      "max-video-preview": -1,
      "max-image-preview": "large",
      "max-snippet": -1,
    },
  },
  generator: "v0.app",
  icons: {
    icon: [
      {
        url: "/icon-light-32x32.png",
        media: "(prefers-color-scheme: light)",
      },
      {
        url: "/icon-dark-32x32.png",
        media: "(prefers-color-scheme: dark)",
      },
      {
        url: "/icon.svg",
        type: "image/svg+xml",
      },
    ],
    apple: "/apple-icon.png",
  },
}

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode
}>) {
  return (
    <html lang="en" className="dark">
      <head>
        <script
          type="application/ld+json"
          dangerouslySetInnerHTML={{
            __html: JSON.stringify({
              "@context": "https://schema.org",
              "@type": "SoftwareApplication",
              name: "Project Zenkai",
              applicationCategory: "HealthApplication",
              operatingSystem: "Web",
              description: "Anime-themed fitness tracker that gamifies your workout and nutrition journey",
              offers: {
                "@type": "Offer",
                price: "0",
                priceCurrency: "USD",
              },
              aggregateRating: {
                "@type": "AggregateRating",
                ratingValue: "4.8",
                ratingCount: "1250",
              },
            }),
          }}
        />
      </head>
      <body className={`${rajdhani.className} antialiased`}>
        {children}
        <Analytics />
      </body>
    </html>
  )
}
```

---

## **app/page.tsx**

```typescriptreact
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { HeroSection } from "@/components/landing/hero-section"
import { FeaturesSection } from "@/components/landing/features-section"
import { HowItWorksSection } from "@/components/landing/how-it-works-section"
import { TestimonialsSection } from "@/components/landing/testimonials-section"
import { PricingSection } from "@/components/landing/pricing-section"
import { CtaSection } from "@/components/landing/cta-section"
import { Footer } from "@/components/landing/footer"

export default function LandingPage() {
  return (
    <div className="min-h-screen bg-background" style={{ backgroundColor: "#1a1a2e", color: "#f8f8f8" }}>
      {/* Navigation */}
      <nav
        className="fixed top-0 z-50 w-full border-b border-border/50 bg-background/80 backdrop-blur-md"
        style={{ backgroundColor: "rgba(26, 26, 46, 0.8)" }}
      >
        <div className="mx-auto flex max-w-7xl items-center justify-between px-4 py-4">
          <Link href="/" className="flex items-center gap-2">
            <div
              className="flex h-10 w-10 items-center justify-center rounded-lg"
              style={{ backgroundColor: "#ff6b35" }}
            >
              <span className="text-xl font-bold" style={{ color: "#1a1a1a" }}>
                Z
              </span>
            </div>
            <span className="text-xl font-bold tracking-tight" style={{ color: "#f8f8f8" }}>
              PROJECT <span style={{ color: "#ff6b35" }}>ZENKAI</span>
            </span>
          </Link>
          <div className="hidden items-center gap-8 md:flex">
            <Link href="#features" className="transition-colors hover:text-foreground" style={{ color: "#a0a0b0" }}>
              Features
            </Link>
            <Link href="#how-it-works" className="transition-colors hover:text-foreground" style={{ color: "#a0a0b0" }}>
              How It Works
            </Link>
            <Link href="#pricing" className="transition-colors hover:text-foreground" style={{ color: "#a0a0b0" }}>
              Pricing
            </Link>
          </div>
          <div className="flex items-center gap-3">
            <Button variant="ghost" asChild>
              <Link href="/login">Log In</Link>
            </Button>
            <Button asChild className="animate-pulse-glow" style={{ backgroundColor: "#ff6b35", color: "#1a1a1a" }}>
              <Link href="/dashboard">Start Training</Link>
            </Button>
          </div>
        </div>
      </nav>

      <main>
        <HeroSection />
        <FeaturesSection />
        <HowItWorksSection />
        <TestimonialsSection />
        <PricingSection />
        <CtaSection />
      </main>

      <Footer />
    </div>
  )
}
```

---

## **app/dashboard/page.tsx**

```typescriptreact
import { StatusWindow } from "@/components/status-window"
import { PowerLevelDisplay } from "@/components/power-level-display"
import { StatBars } from "@/components/stat-bars"
import { TrainingRank } from "@/components/training-rank"
import { AchievementBadges } from "@/components/achievement-badges"
import { DailyQuests } from "@/components/daily-quests"
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { ArrowLeft } from "lucide-react"

// Mock user data - will be replaced with Supabase later
const mockUser = {
  name: "Warrior",
  title: "Rising Champion",
  level: 24,
  currentXP: 7250,
  nextLevelXP: 10000,
  powerLevel: 8420,
  transformationState: "base",
  joinDate: "2024-01-15",
  stats: {
    STR: 45,
    DEX: 38,
    END: 52,
    VIT: 41,
    WIL: 35,
    SPD: 33,
  },
  ranks: {
    push: "B",
    pull: "C",
    legs: "B",
    core: "A",
    cardio: "C",
  },
  achievements: [
    { id: 1, name: "First Blood", description: "Complete your first workout", icon: "sword", unlocked: true },
    { id: 2, name: "Week Warrior", description: "Train 7 days in a row", icon: "flame", unlocked: true },
    { id: 3, name: "Century Club", description: "Log 100 workouts", icon: "trophy", unlocked: false, progress: 67 },
    { id: 4, name: "Iron Will", description: "Train at 5 AM", icon: "sunrise", unlocked: true },
    { id: 5, name: "Limit Breaker", description: "Set 10 personal records", icon: "zap", unlocked: false, progress: 6 },
  ],
  quests: [
    { id: 1, name: "Morning Training", description: "Complete a workout before noon", xp: 150, completed: false },
    { id: 2, name: "Protein Goal", description: "Hit your protein target", xp: 100, completed: true },
    { id: 3, name: "Hydration Master", description: "Log 8 glasses of water", xp: 50, completed: false, progress: 5 },
  ],
}

export default function DashboardPage() {
  return (
    <main className="min-h-screen bg-background p-4 md:p-6 lg:p-8">
      <div className="mx-auto max-w-7xl space-y-6">
        {/* Header */}
        <header className="flex items-center justify-between">
          <div className="flex items-center gap-4">
            <Button variant="ghost" size="icon" asChild>
              <Link href="/">
                <ArrowLeft className="h-5 w-5" />
              </Link>
            </Button>
            <div>
              <h1 className="text-3xl font-bold tracking-tight text-primary md:text-4xl">PROJECT ZENKAI</h1>
              <p className="text-muted-foreground">Status Window</p>
            </div>
          </div>
          <div className="text-right">
            <p className="text-sm text-muted-foreground">Training Day</p>
            <p className="text-2xl font-bold text-accent">#147</p>
          </div>
        </header>

        {/* Main Grid */}
        <div className="grid gap-6 lg:grid-cols-3">
          {/* Left Column - Character Info */}
          <div className="space-y-6 lg:col-span-1">
            <StatusWindow user={mockUser} />
            <TrainingRank ranks={mockUser.ranks} />
          </div>

          {/* Center Column - Stats & Power */}
          <div className="space-y-6 lg:col-span-1">
            <PowerLevelDisplay powerLevel={mockUser.powerLevel} transformationState={mockUser.transformationState} />
            <StatBars stats={mockUser.stats} />
          </div>

          {/* Right Column - Progress & Quests */}
          <div className="space-y-6 lg:col-span-1">
            <DailyQuests quests={mockUser.quests} />
            <AchievementBadges achievements={mockUser.achievements} />
          </div>
        </div>
      </div>
    </main>
  )
}
```

---

## **components/landing/hero-section.tsx**

```typescriptreact
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { Play, Zap, Trophy, TrendingUp } from "lucide-react"

export function HeroSection() {
  return (
    <section className="relative min-h-screen overflow-hidden pt-20">
      {/* Background effects */}
      <div className="absolute inset-0 bg-[radial-gradient(ellipse_at_center,_var(--tw-gradient-stops))] from-primary/20 via-background to-background" />
      <div className="absolute left-1/2 top-1/2 h-[600px] w-[600px] -translate-x-1/2 -translate-y-1/2 rounded-full bg-primary/10 blur-3xl" />
      <div className="absolute right-1/4 top-1/3 h-[300px] w-[300px] rounded-full bg-secondary/10 blur-3xl" />

      <div className="relative mx-auto max-w-7xl px-4 py-20 md:py-32">
        <div className="grid items-center gap-12 lg:grid-cols-2">
          {/* Left content */}
          <div className="space-y-8">
            <div className="inline-flex items-center gap-2 rounded-full border border-primary/30 bg-primary/10 px-4 py-2 text-sm text-primary">
              <Zap className="h-4 w-4" />
              <span>Your Training Arc Begins</span>
            </div>

            <h1 className="text-balance text-5xl font-bold leading-tight tracking-tight md:text-6xl lg:text-7xl">
              <span className="text-foreground">Transform Into</span>
              <br />
              <span className="bg-gradient-to-r from-primary via-accent to-secondary bg-clip-text text-transparent">
                The Main Character
              </span>
            </h1>

            <p className="max-w-lg text-pretty text-lg text-muted-foreground md:text-xl">
              Track workouts, nutrition, and watch your stats grow. Project Zenkai turns your fitness journey into an
              epic anime training arc with RPG mechanics, achievements, and transformation states.
            </p>

            <div className="flex flex-wrap gap-4">
              <Button size="lg" className="animate-pulse-glow gap-2 text-lg" asChild>
                <Link href="/dashboard">
                  <Play className="h-5 w-5" />
                  Start Your Arc
                </Link>
              </Button>
              <Button size="lg" variant="outline" className="gap-2 text-lg bg-transparent" asChild>
                <Link href="#how-it-works">See How It Works</Link>
              </Button>
            </div>

            {/* Stats preview */}
            <div className="flex flex-wrap gap-8 pt-4">
              <div className="space-y-1">
                <p className="text-3xl font-bold text-primary">50K+</p>
                <p className="text-sm text-muted-foreground">Active Warriors</p>
              </div>
              <div className="space-y-1">
                <p className="text-3xl font-bold text-accent">2M+</p>
                <p className="text-sm text-muted-foreground">Workouts Logged</p>
              </div>
              <div className="space-y-1">
                <p className="text-3xl font-bold text-secondary">4.9</p>
                <p className="text-sm text-muted-foreground">App Rating</p>
              </div>
            </div>
          </div>

          {/* Right content - Status window preview */}
          <div className="relative">
            <div className="animate-float relative mx-auto max-w-md">
              {/* Glow effect behind card */}
              <div className="absolute inset-0 rounded-2xl bg-gradient-to-br from-primary/30 via-secondary/20 to-accent/30 blur-2xl" />

              {/* Preview card */}
              <div className="relative rounded-2xl border border-border bg-card p-6 shadow-2xl">
                {/* Corner accents */}
                <div className="absolute left-0 top-0 h-8 w-8 border-l-2 border-t-2 border-primary" />
                <div className="absolute right-0 top-0 h-8 w-8 border-r-2 border-t-2 border-primary" />
                <div className="absolute bottom-0 left-0 h-8 w-8 border-b-2 border-l-2 border-primary" />
                <div className="absolute bottom-0 right-0 h-8 w-8 border-b-2 border-r-2 border-primary" />

                <div className="space-y-6">
                  {/* Header */}
                  <div className="flex items-center justify-between">
                    <div>
                      <p className="text-xs uppercase tracking-wider text-muted-foreground">Status Window</p>
                      <h3 className="text-2xl font-bold text-foreground">WARRIOR</h3>
                      <p className="text-sm text-primary">Rising Champion</p>
                    </div>
                    <div className="text-right">
                      <p className="text-4xl font-bold text-accent">24</p>
                      <p className="text-xs text-muted-foreground">LEVEL</p>
                    </div>
                  </div>

                  {/* Power Level */}
                  <div className="rounded-lg border border-primary/30 bg-primary/10 p-4 text-center">
                    <p className="text-xs uppercase tracking-wider text-primary">Power Level</p>
                    <p className="animate-power-surge text-4xl font-bold text-primary">8,420</p>
                  </div>

                  {/* Stats preview */}
                  <div className="grid grid-cols-3 gap-3">
                    {[
                      { label: "STR", value: 45, color: "bg-primary" },
                      { label: "END", value: 52, color: "bg-secondary" },
                      { label: "VIT", value: 41, color: "bg-accent" },
                    ].map((stat) => (
                      <div key={stat.label} className="space-y-1">
                        <div className="flex justify-between text-xs">
                          <span className="text-muted-foreground">{stat.label}</span>
                          <span className="font-bold">{stat.value}</span>
                        </div>
                        <div className="h-2 overflow-hidden rounded-full bg-muted">
                          <div className={`h-full ${stat.color}`} style={{ width: `${stat.value}%` }} />
                        </div>
                      </div>
                    ))}
                  </div>

                  {/* Achievement icons */}
                  <div className="flex items-center justify-center gap-3">
                    <div className="flex h-10 w-10 items-center justify-center rounded-full bg-primary/20 text-primary">
                      <Trophy className="h-5 w-5" />
                    </div>
                    <div className="flex h-10 w-10 items-center justify-center rounded-full bg-accent/20 text-accent">
                      <Zap className="h-5 w-5" />
                    </div>
                    <div className="flex h-10 w-10 items-center justify-center rounded-full bg-secondary/20 text-secondary">
                      <TrendingUp className="h-5 w-5" />
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/features-section.tsx**

```typescriptreact
import { Dumbbell, Utensils, Trophy, TrendingUp, Users, Sparkles } from "lucide-react"

const features = [
  {
    icon: Dumbbell,
    title: "Training Arcs",
    description:
      "Log sets, reps, and RPE with precision. Watch your lifts rank up from F to S as you progress through your training arc.",
    color: "text-primary",
    bgColor: "bg-primary/10",
  },
  {
    icon: Utensils,
    title: "Sustenance Mode",
    description:
      "Track calories and macros with Ki/Chakra theming. Build your perfect meal plan and fuel your transformation.",
    color: "text-accent",
    bgColor: "bg-accent/10",
  },
  {
    icon: Trophy,
    title: "Achievement System",
    description:
      "Unlock badges and titles as you hit milestones. From 'First Blood' to 'Legendary Warrior' - every achievement tells your story.",
    color: "text-secondary",
    bgColor: "bg-secondary/10",
  },
  {
    icon: TrendingUp,
    title: "Stat Progression",
    description:
      "Watch your STR, DEX, END, VIT, WIL, and SPD grow with each workout. Real progress reflected in RPG-style stats.",
    color: "text-primary",
    bgColor: "bg-primary/10",
  },
  {
    icon: Sparkles,
    title: "Transformation States",
    description:
      "Unlock new forms as you level up. Start at Base, evolve through Awakened, and reach your Ultimate transformation.",
    color: "text-accent",
    bgColor: "bg-accent/10",
  },
  {
    icon: Users,
    title: "Guild System",
    description:
      "Join or create training guilds. Complete group challenges, compete on leaderboards, and support fellow warriors.",
    color: "text-secondary",
    bgColor: "bg-secondary/10",
  },
]

export function FeaturesSection() {
  return (
    <section id="features" className="relative py-20 md:py-32">
      <div className="mx-auto max-w-7xl px-4">
        <div className="mx-auto max-w-2xl text-center">
          <h2 className="text-3xl font-bold tracking-tight md:text-4xl lg:text-5xl">
            <span className="text-foreground">Everything You Need to</span>
            <br />
            <span className="text-primary">Level Up</span>
          </h2>
          <p className="mt-4 text-lg text-muted-foreground">
            Combining the precision of professional fitness tracking with the motivation of anime-style gamification.
          </p>
        </div>

        <div className="mt-16 grid gap-8 md:grid-cols-2 lg:grid-cols-3">
          {features.map((feature) => (
            <div
              key={feature.title}
              className="group relative rounded-xl border border-border bg-card p-6 transition-all hover:border-primary/50 hover:shadow-lg hover:shadow-primary/5"
            >
              {/* Icon */}
              <div
                className={`inline-flex h-12 w-12 items-center justify-center rounded-lg ${feature.bgColor} ${feature.color}`}
              >
                <feature.icon className="h-6 w-6" />
              </div>

              {/* Content */}
              <h3 className="mt-4 text-xl font-bold text-foreground">{feature.title}</h3>
              <p className="mt-2 text-muted-foreground">{feature.description}</p>

              {/* Hover glow effect */}
              <div className="absolute inset-0 -z-10 rounded-xl bg-gradient-to-br from-primary/5 to-transparent opacity-0 transition-opacity group-hover:opacity-100" />
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/how-it-works-section.tsx**

```typescriptreact
import { UserPlus, Target, TrendingUp, Crown } from "lucide-react"

const steps = [
  {
    number: "01",
    icon: UserPlus,
    title: "Create Your Character",
    description: "Sign up and set your fitness goals. Choose your starting class and customize your warrior profile.",
  },
  {
    number: "02",
    icon: Target,
    title: "Accept Daily Quests",
    description:
      "Receive personalized training quests based on your goals. Complete them to earn XP and unlock rewards.",
  },
  {
    number: "03",
    icon: TrendingUp,
    title: "Train & Level Up",
    description:
      "Log workouts and meals. Watch your stats grow and your power level increase with each completed session.",
  },
  {
    number: "04",
    icon: Crown,
    title: "Achieve Transformation",
    description:
      "Reach milestones to unlock new transformation states. Become the legendary warrior you were meant to be.",
  },
]

export function HowItWorksSection() {
  return (
    <section id="how-it-works" className="relative bg-muted/30 py-20 md:py-32">
      <div className="mx-auto max-w-7xl px-4">
        <div className="mx-auto max-w-2xl text-center">
          <h2 className="text-3xl font-bold tracking-tight md:text-4xl lg:text-5xl">
            <span className="text-foreground">Your Path to</span> <span className="text-primary">Greatness</span>
          </h2>
          <p className="mt-4 text-lg text-muted-foreground">
            Four simple steps to transform your fitness journey into an epic adventure.
          </p>
        </div>

        <div className="mt-16 grid gap-8 md:grid-cols-2 lg:grid-cols-4">
          {steps.map((step, index) => (
            <div key={step.number} className="relative">
              {/* Connector line */}
              {index < steps.length - 1 && (
                <div className="absolute left-1/2 top-12 hidden h-0.5 w-full bg-gradient-to-r from-primary to-transparent lg:block" />
              )}

              <div className="relative flex flex-col items-center text-center">
                {/* Number badge */}
                <div className="relative">
                  <div className="flex h-24 w-24 items-center justify-center rounded-full border-2 border-primary bg-card">
                    <step.icon className="h-10 w-10 text-primary" />
                  </div>
                  <span className="absolute -right-2 -top-2 flex h-8 w-8 items-center justify-center rounded-full bg-primary text-sm font-bold text-primary-foreground">
                    {step.number}
                  </span>
                </div>

                {/* Content */}
                <h3 className="mt-6 text-xl font-bold text-foreground">{step.title}</h3>
                <p className="mt-2 text-muted-foreground">{step.description}</p>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/testimonials-section.tsx**

```typescriptreact
import { Star } from "lucide-react"

const testimonials = [
  {
    name: "Alex K.",
    title: "Level 47 Warrior",
    avatar: "A",
    content:
      "I've tried every fitness app out there. Project Zenkai is the only one that kept me motivated for more than a month. Seeing my stats grow like an RPG character is incredibly addicting!",
    rating: 5,
  },
  {
    name: "Sarah M.",
    title: "Level 32 Assassin",
    avatar: "S",
    content:
      "The daily quest system completely changed how I approach fitness. I actually look forward to working out now because I want to complete my quests and level up.",
    rating: 5,
  },
  {
    name: "Mike T.",
    title: "Level 56 Berserker",
    avatar: "M",
    content:
      "As a huge anime fan, this app speaks my language. The transformation system is genius - I'm grinding hard to unlock my 'Super Saiyan' state!",
    rating: 5,
  },
]

export function TestimonialsSection() {
  return (
    <section className="py-20 md:py-32">
      <div className="mx-auto max-w-7xl px-4">
        <div className="mx-auto max-w-2xl text-center">
          <h2 className="text-3xl font-bold tracking-tight md:text-4xl lg:text-5xl">
            <span className="text-foreground">Warriors Who</span> <span className="text-primary">Leveled Up</span>
          </h2>
          <p className="mt-4 text-lg text-muted-foreground">
            Join thousands of warriors who transformed their fitness journey.
          </p>
        </div>

        <div className="mt-16 grid gap-8 md:grid-cols-3">
          {testimonials.map((testimonial) => (
            <div key={testimonial.name} className="relative rounded-xl border border-border bg-card p-6">
              {/* Quote decoration */}
              <div className="absolute -top-3 left-6 text-5xl text-primary/20">&quot;</div>

              {/* Rating */}
              <div className="flex gap-1">
                {Array.from({ length: testimonial.rating }).map((_, i) => (
                  <Star key={i} className="h-4 w-4 fill-accent text-accent" />
                ))}
              </div>

              {/* Content */}
              <p className="mt-4 text-muted-foreground">{testimonial.content}</p>

              {/* Author */}
              <div className="mt-6 flex items-center gap-3">
                <div className="flex h-10 w-10 items-center justify-center rounded-full bg-primary text-sm font-bold text-primary-foreground">
                  {testimonial.avatar}
                </div>
                <div>
                  <p className="font-semibold text-foreground">{testimonial.name}</p>
                  <p className="text-sm text-primary">{testimonial.title}</p>
                </div>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/pricing-section.tsx**

```typescriptreact
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { Check } from "lucide-react"

const plans = [
  {
    name: "Apprentice",
    price: "Free",
    description: "Perfect for starting your training arc",
    features: [
      "Basic workout tracking",
      "Calorie counting",
      "5 daily quests",
      "Basic stat progression",
      "10 achievements",
    ],
    cta: "Start Free",
    popular: false,
  },
  {
    name: "Elite Warrior",
    price: "$9.99",
    period: "/month",
    description: "For serious warriors ready to transform",
    features: [
      "Unlimited workout tracking",
      "Full macro tracking",
      "Unlimited daily quests",
      "Advanced stat analytics",
      "All achievements unlocked",
      "Transformation states",
      "Guild creation & management",
      "Priority support",
    ],
    cta: "Begin Transformation",
    popular: true,
  },
  {
    name: "Legendary",
    price: "$79.99",
    period: "/year",
    description: "The ultimate warrior package",
    features: [
      "Everything in Elite Warrior",
      "Custom workout programs",
      "AI-powered meal planning",
      "Exclusive legendary achievements",
      "Early access to new features",
      "1-on-1 coaching sessions",
    ],
    cta: "Go Legendary",
    popular: false,
  },
]

export function PricingSection() {
  return (
    <section id="pricing" className="relative bg-muted/30 py-20 md:py-32">
      <div className="mx-auto max-w-7xl px-4">
        <div className="mx-auto max-w-2xl text-center">
          <h2 className="text-3xl font-bold tracking-tight md:text-4xl lg:text-5xl">
            <span className="text-foreground">Choose Your</span> <span className="text-primary">Power Level</span>
          </h2>
          <p className="mt-4 text-lg text-muted-foreground">Start free and upgrade as you grow stronger.</p>
        </div>

        <div className="mt-16 grid gap-8 lg:grid-cols-3">
          {plans.map((plan) => (
            <div
              key={plan.name}
              className={`relative rounded-xl border bg-card p-8 ${
                plan.popular ? "border-primary shadow-lg shadow-primary/20" : "border-border"
              }`}
            >
              {/* Popular badge */}
              {plan.popular && (
                <div className="absolute -top-3 left-1/2 -translate-x-1/2 rounded-full bg-primary px-4 py-1 text-sm font-semibold text-primary-foreground">
                  Most Popular
                </div>
              )}

              {/* Header */}
              <div className="text-center">
                <h3 className="text-xl font-bold text-foreground">{plan.name}</h3>
                <div className="mt-4">
                  <span className="text-4xl font-bold text-foreground">{plan.price}</span>
                  {plan.period && <span className="text-muted-foreground">{plan.period}</span>}
                </div>
                <p className="mt-2 text-sm text-muted-foreground">{plan.description}</p>
              </div>

              {/* Features */}
              <ul className="mt-8 space-y-3">
                {plan.features.map((feature) => (
                  <li key={feature} className="flex items-center gap-3">
                    <Check className="h-5 w-5 text-primary" />
                    <span className="text-muted-foreground">{feature}</span>
                  </li>
                ))}
              </ul>

              {/* CTA */}
              <Button
                className={`mt-8 w-full ${plan.popular ? "animate-pulse-glow" : ""}`}
                variant={plan.popular ? "default" : "outline"}
                asChild
              >
                <Link href="/dashboard">{plan.cta}</Link>
              </Button>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/cta-section.tsx**

```typescriptreact
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { Zap } from "lucide-react"

export function CtaSection() {
  return (
    <section className="relative py-20 md:py-32">
      <div className="mx-auto max-w-7xl px-4">
        <div className="relative overflow-hidden rounded-2xl bg-gradient-to-br from-primary/20 via-card to-secondary/20 p-8 md:p-16">
          {/* Background effects */}
          <div className="absolute left-0 top-0 h-64 w-64 rounded-full bg-primary/20 blur-3xl" />
          <div className="absolute bottom-0 right-0 h-64 w-64 rounded-full bg-secondary/20 blur-3xl" />

          {/* Corner accents */}
          <div className="absolute left-0 top-0 h-16 w-16 border-l-4 border-t-4 border-primary" />
          <div className="absolute right-0 top-0 h-16 w-16 border-r-4 border-t-4 border-primary" />
          <div className="absolute bottom-0 left-0 h-16 w-16 border-b-4 border-l-4 border-primary" />
          <div className="absolute bottom-0 right-0 h-16 w-16 border-b-4 border-r-4 border-primary" />

          <div className="relative mx-auto max-w-2xl text-center">
            <div className="inline-flex items-center gap-2 rounded-full border border-accent/30 bg-accent/10 px-4 py-2 text-sm text-accent">
              <Zap className="h-4 w-4" />
              <span>Limited Time: 50% Off First Month</span>
            </div>

            <h2 className="mt-6 text-3xl font-bold tracking-tight md:text-4xl lg:text-5xl">
              <span className="text-foreground">Ready to Begin Your</span>
              <br />
              <span className="text-primary">Training Arc?</span>
            </h2>

            <p className="mt-4 text-lg text-muted-foreground">
              Join 50,000+ warriors who have already started their transformation. Your journey to becoming the main
              character starts now.
            </p>

            <div className="mt-8 flex flex-wrap justify-center gap-4">
              <Button size="lg" className="animate-pulse-glow gap-2 text-lg" asChild>
                <Link href="/dashboard">
                  <Zap className="h-5 w-5" />
                  Start Training Now
                </Link>
              </Button>
            </div>

            <p className="mt-6 text-sm text-muted-foreground">No credit card required. Start free, upgrade anytime.</p>
          </div>
        </div>
      </div>
    </section>
  )
}
```

---

## **components/landing/footer.tsx**

```typescriptreact
import Link from "next/link"
import { Github, Twitter } from "lucide-react"

export function Footer() {
  return (
    <footer className="border-t border-border bg-card py-12">
      <div className="mx-auto max-w-7xl px-4">
        <div className="grid gap-8 md:grid-cols-4">
          {/* Brand */}
          <div className="space-y-4">
            <Link href="/" className="flex items-center gap-2">
              <div className="flex h-8 w-8 items-center justify-center rounded-lg bg-primary">
                <span className="text-lg font-bold text-primary-foreground">Z</span>
              </div>
              <span className="text-lg font-bold tracking-tight text-foreground">
                PROJECT <span className="text-primary">ZENKAI</span>
              </span>
            </Link>
            <p className="text-sm text-muted-foreground">Transform your fitness journey into an anime training arc.</p>
            <div className="flex gap-4">
              <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                <Twitter className="h-5 w-5" />
              </Link>
              <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                <Github className="h-5 w-5" />
              </Link>
            </div>
          </div>

          {/* Product */}
          <div>
            <h4 className="mb-4 font-semibold text-foreground">Product</h4>
            <ul className="space-y-2 text-sm">
              <li>
                <Link href="#features" className="text-muted-foreground transition-colors hover:text-foreground">
                  Features
                </Link>
              </li>
              <li>
                <Link href="#pricing" className="text-muted-foreground transition-colors hover:text-foreground">
                  Pricing
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Roadmap
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Changelog
                </Link>
              </li>
            </ul>
          </div>

          {/* Resources */}
          <div>
            <h4 className="mb-4 font-semibold text-foreground">Resources</h4>
            <ul className="space-y-2 text-sm">
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Blog
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Help Center
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Community
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  API Docs
                </Link>
              </li>
            </ul>
          </div>

          {/* Legal */}
          <div>
            <h4 className="mb-4 font-semibold text-foreground">Legal</h4>
            <ul className="space-y-2 text-sm">
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Privacy Policy
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Terms of Service
                </Link>
              </li>
              <li>
                <Link href="#" className="text-muted-foreground transition-colors hover:text-foreground">
                  Cookie Policy
                </Link>
              </li>
            </ul>
          </div>
        </div>

        <div className="mt-12 border-t border-border pt-8 text-center text-sm text-muted-foreground">
          <p>&copy; {new Date().getFullYear()} Project Zenkai. All rights reserved.</p>
        </div>
      </div>
    </footer>
  )
}
```

---

## **components/status-window.tsx**

```typescriptreact
"use client"

import { Card, CardContent, CardHeader } from "@/components/ui/card"
import { User, Calendar, Star } from "lucide-react"

interface StatusWindowProps {
  user: {
    name: string
    title: string
    level: number
    currentXP: number
    nextLevelXP: number
    joinDate: string
  }
}

export function StatusWindow({ user }: StatusWindowProps) {
  const xpProgress = (user.currentXP / user.nextLevelXP) * 100
  const daysSinceJoin = Math.floor((new Date().getTime() - new Date(user.joinDate).getTime()) / (1000 * 60 * 60 * 24))

  return (
    <Card className="relative overflow-hidden border-2 border-primary/50 bg-card/80 backdrop-blur animate-pulse-glow">
      {/* Corner accents */}
      <div className="absolute left-0 top-0 h-4 w-4 border-l-2 border-t-2 border-primary" />
      <div className="absolute right-0 top-0 h-4 w-4 border-r-2 border-t-2 border-primary" />
      <div className="absolute bottom-0 left-0 h-4 w-4 border-b-2 border-l-2 border-primary" />
      <div className="absolute bottom-0 right-0 h-4 w-4 border-b-2 border-r-2 border-primary" />

      <CardHeader className="pb-2">
        <div className="flex items-center justify-between">
          <span className="text-xs font-semibold uppercase tracking-widest text-primary">Status Window</span>
          <span className="rounded bg-primary/20 px-2 py-0.5 text-xs font-bold text-primary">ACTIVE</span>
        </div>
      </CardHeader>

      <CardContent className="space-y-4">
        {/* Avatar & Name */}
        <div className="flex items-center gap-4">
          <div className="relative">
            <div className="flex h-16 w-16 items-center justify-center rounded-full border-2 border-primary bg-primary/20">
              <User className="h-8 w-8 text-primary" />
            </div>
            <div className="absolute -bottom-1 -right-1 flex h-6 w-6 items-center justify-center rounded-full border-2 border-background bg-accent text-xs font-bold text-accent-foreground">
              {user.level}
            </div>
          </div>
          <div className="flex-1">
            <h2 className="text-xl font-bold text-foreground">{user.name}</h2>
            <p className="text-sm text-secondary">{user.title}</p>
          </div>
        </div>

        {/* Level Progress */}
        <div className="space-y-2">
          <div className="flex items-center justify-between text-sm">
            <span className="flex items-center gap-1 text-muted-foreground">
              <Star className="h-4 w-4 text-accent" />
              Level {user.level}
            </span>
            <span className="font-mono text-xs text-muted-foreground">
              {user.currentXP.toLocaleString()} / {user.nextLevelXP.toLocaleString()} XP
            </span>
          </div>
          <div className="relative h-3 overflow-hidden rounded-full bg-muted">
            <div
              className="absolute inset-y-0 left-0 rounded-full bg-gradient-to-r from-primary to-accent animate-energy-flow"
              style={{ width: `${xpProgress}%` }}
            />
          </div>
          <p className="text-center text-xs text-muted-foreground">
            {(user.nextLevelXP - user.currentXP).toLocaleString()} XP to next level
          </p>
        </div>

        {/* Join Date */}
        <div className="flex items-center justify-between rounded-lg bg-muted/50 px-3 py-2 text-sm">
          <span className="flex items-center gap-2 text-muted-foreground">
            <Calendar className="h-4 w-4" />
            Training Since
          </span>
          <span className="font-semibold text-foreground">{daysSinceJoin} Days</span>
        </div>
      </CardContent>
    </Card>
  )
}
```

---

## **components/power-level-display.tsx**

```typescriptreact
"use client"

import { Card, CardContent } from "@/components/ui/card"
import { Zap } from "lucide-react"

interface PowerLevelDisplayProps {
  powerLevel: number
  transformationState: string
}

const transformationColors: Record<string, { bg: string; text: string; glow: string }> = {
  base: {
    bg: "from-primary/20 to-secondary/20",
    text: "text-primary",
    glow: "shadow-[0_0_60px_rgba(255,165,0,0.3)]",
  },
  ssj: {
    bg: "from-accent/30 to-yellow-500/20",
    text: "text-accent",
    glow: "shadow-[0_0_80px_rgba(255,215,0,0.5)]",
  },
  ssb: {
    bg: "from-secondary/30 to-blue-400/20",
    text: "text-secondary",
    glow: "shadow-[0_0_80px_rgba(0,150,255,0.5)]",
  },
}

export function PowerLevelDisplay({ powerLevel, transformationState }: PowerLevelDisplayProps) {
  const colors = transformationColors[transformationState] || transformationColors.base

  const formattedPower = powerLevel.toLocaleString()

  return (
    <Card className={`relative overflow-hidden border-2 border-primary/30 ${colors.glow} animate-power-surge`}>
      {/* Animated background */}
      <div className={`absolute inset-0 bg-gradient-to-br ${colors.bg} animate-energy-flow`} />

      {/* Scan lines effect */}
      <div
        className="absolute inset-0 opacity-10"
        style={{
          backgroundImage:
            "repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255,255,255,0.1) 2px, rgba(255,255,255,0.1) 4px)",
        }}
      />

      <CardContent className="relative flex flex-col items-center justify-center py-8">
        {/* Scouter-style label */}
        <div className="mb-2 flex items-center gap-2">
          <Zap className="h-5 w-5 text-primary" />
          <span className="text-xs font-semibold uppercase tracking-[0.3em] text-muted-foreground">Power Level</span>
          <Zap className="h-5 w-5 text-primary" />
        </div>

        {/* Main power display */}
        <div className="relative">
          <p className={`text-6xl font-bold tracking-wider ${colors.text} md:text-7xl`}>{formattedPower}</p>
          {/* Glow effect behind text */}
          <p
            className={`absolute inset-0 text-6xl font-bold tracking-wider ${colors.text} blur-sm opacity-50 md:text-7xl`}
          >
            {formattedPower}
          </p>
        </div>

        {/* Transformation state */}
        <div className="mt-4 flex items-center gap-2">
          <span className="text-sm uppercase tracking-wide text-muted-foreground">Form:</span>
          <span
            className={`rounded-full border px-3 py-1 text-sm font-bold uppercase ${
              transformationState === "base"
                ? "border-primary/50 bg-primary/10 text-primary"
                : transformationState === "ssj"
                  ? "border-accent/50 bg-accent/10 text-accent"
                  : "border-secondary/50 bg-secondary/10 text-secondary"
            }`}
          >
            {transformationState === "base" ? "Base" : transformationState.toUpperCase()}
          </span>
        </div>

        {/* Power tier indicator */}
        <p className="mt-2 text-xs text-muted-foreground">
          {powerLevel < 5000 && "Tier: Earthling"}
          {powerLevel >= 5000 && powerLevel < 10000 && "Tier: Elite Warrior"}
          {powerLevel >= 10000 && powerLevel < 50000 && "Tier: Super Elite"}
          {powerLevel >= 50000 && "Tier: Legendary"}
        </p>
      </CardContent>
    </Card>
  )
}
```

---

## **components/stat-bars.tsx**

```typescriptreact
"use client"

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { Dumbbell, Target, Heart, Shield, Brain, Gauge } from "lucide-react"

interface StatBarsProps {
  stats: {
    STR: number
    DEX: number
    END: number
    VIT: number
    WIL: number
    SPD: number
  }
}

const statConfig = {
  STR: { label: "Strength", icon: Dumbbell, color: "bg-red-500", description: "Raw power output" },
  DEX: { label: "Dexterity", icon: Target, color: "bg-green-500", description: "Precision & form" },
  END: { label: "Endurance", icon: Heart, color: "bg-blue-500", description: "Stamina & recovery" },
  VIT: { label: "Vitality", icon: Shield, color: "bg-pink-500", description: "Overall health" },
  WIL: { label: "Willpower", icon: Brain, color: "bg-purple-500", description: "Mental fortitude" },
  SPD: { label: "Speed", icon: Gauge, color: "bg-yellow-500", description: "Explosive power" },
}

export function StatBars({ stats }: StatBarsProps) {
  const maxStat = 100

  return (
    <Card className="border-2 border-secondary/30 bg-card/80 backdrop-blur">
      <CardHeader className="pb-2">
        <CardTitle className="flex items-center gap-2 text-lg">
          <span className="text-secondary">{"<"}</span>
          Core Attributes
          <span className="text-secondary">{">"}</span>
        </CardTitle>
      </CardHeader>
      <CardContent className="space-y-3">
        {(Object.entries(stats) as [keyof typeof statConfig, number][]).map(([key, value]) => {
          const config = statConfig[key]
          const Icon = config.icon
          const percentage = (value / maxStat) * 100

          return (
            <div key={key} className="group">
              <div className="mb-1 flex items-center justify-between">
                <div className="flex items-center gap-2">
                  <Icon className="h-4 w-4 text-muted-foreground" />
                  <span className="text-sm font-semibold">{config.label}</span>
                  <span className="text-xs text-muted-foreground opacity-0 transition-opacity group-hover:opacity-100">
                    {config.description}
                  </span>
                </div>
                <span className="font-mono text-sm font-bold text-foreground">{value}</span>
              </div>
              <div className="relative h-2 overflow-hidden rounded-full bg-muted">
                <div
                  className={`absolute inset-y-0 left-0 rounded-full ${config.color} transition-all duration-500`}
                  style={{ width: `${percentage}%` }}
                />
                {/* Shine effect */}
                <div
                  className="absolute inset-y-0 left-0 rounded-full bg-gradient-to-r from-transparent via-white/30 to-transparent"
                  style={{ width: `${percentage}%` }}
                />
              </div>
            </div>
          )
        })}

        {/* Total stat points */}
        <div className="mt-4 flex items-center justify-between rounded-lg bg-muted/50 px-3 py-2">
          <span className="text-sm text-muted-foreground">Total Stat Points</span>
          <span className="font-mono text-lg font-bold text-accent">
            {Object.values(stats).reduce((a, b) => a + b, 0)}
          </span>
        </div>
      </CardContent>
    </Card>
  )
}
```

---

## **components/training-rank.tsx**

```typescriptreact
"use client"

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"

interface TrainingRankProps {
  ranks: {
    push: string
    pull: string
    legs: string
    core: string
    cardio: string
  }
}

const rankColors: Record<string, { bg: string; border: string; text: string }> = {
  S: { bg: "bg-gradient-to-br from-amber-400 to-orange-500", border: "border-amber-400", text: "text-black" },
  A: { bg: "bg-gradient-to-br from-red-500 to-rose-600", border: "border-red-500", text: "text-white" },
  B: { bg: "bg-gradient-to-br from-blue-500 to-indigo-600", border: "border-blue-500", text: "text-white" },
  C: { bg: "bg-gradient-to-br from-green-500 to-emerald-600", border: "border-green-500", text: "text-white" },
  D: { bg: "bg-gradient-to-br from-gray-400 to-gray-500", border: "border-gray-400", text: "text-white" },
  F: { bg: "bg-gradient-to-br from-gray-600 to-gray-700", border: "border-gray-600", text: "text-gray-300" },
}

const categoryLabels: Record<string, string> = {
  push: "Push",
  pull: "Pull",
  legs: "Legs",
  core: "Core",
  cardio: "Cardio",
}

export function TrainingRank({ ranks }: TrainingRankProps) {
  return (
    <Card className="border-2 border-accent/30 bg-card/80 backdrop-blur">
      <CardHeader className="pb-2">
        <CardTitle className="flex items-center gap-2 text-lg">
          <span className="text-accent">{"["}</span>
          Training Ranks
          <span className="text-accent">{"]"}</span>
        </CardTitle>
      </CardHeader>
      <CardContent>
        <div className="grid grid-cols-5 gap-2">
          {(Object.entries(ranks) as [keyof typeof categoryLabels, string][]).map(([category, rank]) => {
            const colors = rankColors[rank] || rankColors.F
            return (
              <div key={category} className="flex flex-col items-center gap-1">
                <div
                  className={`flex h-12 w-12 items-center justify-center rounded-lg border-2 ${colors.bg} ${colors.border} ${colors.text} text-xl font-black shadow-lg`}
                >
                  {rank}
                </div>
                <span className="text-xs font-medium text-muted-foreground">{categoryLabels[category]}</span>
              </div>
            )
          })}
        </div>

        {/* Rank legend */}
        <div className="mt-4 flex flex-wrap items-center justify-center gap-2 text-xs text-muted-foreground">
          <span className="text-amber-400">S</span>
          <span>{">"}</span>
          <span className="text-red-500">A</span>
          <span>{">"}</span>
          <span className="text-blue-500">B</span>
          <span>{">"}</span>
          <span className="text-green-500">C</span>
          <span>{">"}</span>
          <span className="text-gray-400">D</span>
          <span>{">"}</span>
          <span className="text-gray-600">F</span>
        </div>
      </CardContent>
    </Card>
  )
}
```

---

## **components/daily-quests.tsx**

```typescriptreact
"use client"

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { Progress } from "@/components/ui/progress"
import { Check, Circle, Sparkles } from "lucide-react"

interface Quest {
  id: number
  name: string
  description: string
  xp: number
  completed: boolean
  progress?: number
}

interface DailyQuestsProps {
  quests: Quest[]
}

export function DailyQuests({ quests }: DailyQuestsProps) {
  const completedCount = quests.filter((q) => q.completed).length
  const totalXP = quests.reduce((acc, q) => acc + (q.completed ? q.xp : 0), 0)
  const potentialXP = quests.reduce((acc, q) => acc + q.xp, 0)

  return (
    <Card className="border-2 border-primary/30 bg-card/80 backdrop-blur">
      <CardHeader className="pb-2">
        <div className="flex items-center justify-between">
          <CardTitle className="flex items-center gap-2 text-lg">
            <Sparkles className="h-5 w-5 text-primary" />
            Daily Quests
          </CardTitle>
          <span className="rounded-full bg-primary/20 px-2 py-0.5 text-xs font-bold text-primary">
            {completedCount}/{quests.length}
          </span>
        </div>
      </CardHeader>
      <CardContent className="space-y-3">
        {quests.map((quest) => (
          <div
            key={quest.id}
            className={`rounded-lg border p-3 transition-all ${
              quest.completed
                ? "border-green-500/50 bg-green-500/10"
                : "border-border bg-muted/30 hover:border-primary/50"
            }`}
          >
            <div className="flex items-start gap-3">
              <div
                className={`mt-0.5 flex h-5 w-5 items-center justify-center rounded-full border-2 ${
                  quest.completed ? "border-green-500 bg-green-500 text-black" : "border-muted-foreground"
                }`}
              >
                {quest.completed ? <Check className="h-3 w-3" /> : <Circle className="h-3 w-3 opacity-0" />}
              </div>
              <div className="flex-1">
                <div className="flex items-center justify-between">
                  <h3
                    className={`font-semibold ${quest.completed ? "text-green-400 line-through" : "text-foreground"}`}
                  >
                    {quest.name}
                  </h3>
                  <span className={`text-xs font-bold ${quest.completed ? "text-green-400" : "text-accent"}`}>
                    +{quest.xp} XP
                  </span>
                </div>
                <p className="text-xs text-muted-foreground">{quest.description}</p>

                {/* Progress bar for quests with progress */}
                {quest.progress !== undefined && !quest.completed && (
                  <div className="mt-2">
                    <Progress value={(quest.progress / 8) * 100} className="h-1.5" />
                    <p className="mt-1 text-xs text-muted-foreground">{quest.progress}/8</p>
                  </div>
                )}
              </div>
            </div>
          </div>
        ))}

        {/* XP Summary */}
        <div className="mt-4 flex items-center justify-between rounded-lg bg-primary/10 px-3 py-2">
          <span className="text-sm text-muted-foreground">Today{"'"}s XP</span>
          <span className="font-mono font-bold">
            <span className="text-primary">{totalXP}</span>
            <span className="text-muted-foreground"> / {potentialXP}</span>
          </span>
        </div>
      </CardContent>
    </Card>
  )
}
```

---

## **components/achievement-badges.tsx**

```typescriptreact
"use client"

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { Sword, Flame, Trophy, Sunrise, Zap, Lock } from "lucide-react"

interface Achievement {
  id: number
  name: string
  description: string
  icon: string
  unlocked: boolean
  progress?: number
}

interface AchievementBadgesProps {
  achievements: Achievement[]
}

const iconMap: Record<string, typeof Sword> = {
  sword: Sword,
  flame: Flame,
  trophy: Trophy,
  sunrise: Sunrise,
  zap: Zap,
}

export function AchievementBadges({ achievements }: AchievementBadgesProps) {
  const unlockedCount = achievements.filter((a) => a.unlocked).length

  return (
    <Card className="border-2 border-accent/30 bg-card/80 backdrop-blur">
      <CardHeader className="pb-2">
        <div className="flex items-center justify-between">
          <CardTitle className="flex items-center gap-2 text-lg">
            <Trophy className="h-5 w-5 text-accent" />
            Achievements
          </CardTitle>
          <span className="rounded-full bg-accent/20 px-2 py-0.5 text-xs font-bold text-accent">
            {unlockedCount}/{achievements.length}
          </span>
        </div>
      </CardHeader>
      <CardContent>
        <div className="grid grid-cols-5 gap-2">
          {achievements.map((achievement) => {
            const Icon = iconMap[achievement.icon] || Trophy

            return (
              <div
                key={achievement.id}
                className="group relative flex flex-col items-center"
                title={`${achievement.name}: ${achievement.description}`}
              >
                <div
                  className={`relative flex h-12 w-12 items-center justify-center rounded-full border-2 transition-all ${
                    achievement.unlocked
                      ? "border-accent bg-gradient-to-br from-accent/30 to-primary/30 shadow-[0_0_15px_rgba(255,215,0,0.3)]"
                      : "border-muted bg-muted/50 grayscale"
                  }`}
                >
                  {achievement.unlocked ? (
                    <Icon className="h-5 w-5 text-accent" />
                  ) : (
                    <Lock className="h-4 w-4 text-muted-foreground" />
                  )}

                  {/* Progress ring for locked achievements */}
                  {!achievement.unlocked && achievement.progress !== undefined && (
                    <svg className="absolute inset-0 -rotate-90" viewBox="0 0 48 48">
                      <circle
                        cx="24"
                        cy="24"
                        r="22"
                        fill="none"
                        stroke="currentColor"
                        strokeWidth="2"
                        className="text-primary/30"
                        strokeDasharray={`${(achievement.progress / 10) * 138} 138`}
                      />
                    </svg>
                  )}
                </div>

                {/* Tooltip on hover */}
                <div className="pointer-events-none absolute -top-16 left-1/2 z-10 w-32 -translate-x-1/2 rounded-lg bg-popover p-2 text-center opacity-0 shadow-lg transition-opacity group-hover:opacity-100">
                  <p className="text-xs font-semibold text-foreground">{achievement.name}</p>
                  <p className="text-[10px] text-muted-foreground">{achievement.description}</p>
                  {achievement.progress !== undefined && !achievement.unlocked && (
                    <p className="mt-1 text-[10px] text-primary">{achievement.progress}/10</p>
                  )}
                </div>
              </div>
            )
          })}
        </div>

        {/* Recent unlock */}
        <div className="mt-4 rounded-lg border border-accent/30 bg-accent/5 p-3">
          <p className="text-xs text-muted-foreground">Latest Unlock</p>
          <div className="mt-1 flex items-center gap-2">
            <Flame className="h-4 w-4 text-accent" />
            <span className="text-sm font-semibold text-foreground">Week Warrior</span>
          </div>
        </div>
      </CardContent>
    </Card>
  )
}
```

---

That's all 17 files for the complete Project Zenkai codebase. Copy each file into the corresponding path in your Next.js project. Make sure you have the shadcn/ui components installed (`card`, `button`, `progress`) and Tailwind CSS configured.