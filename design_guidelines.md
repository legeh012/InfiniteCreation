# Reality TV Episode Generator - Design Guidelines

## Design Approach

**Selected Approach:** Production Tool Design Pattern inspired by modern AI creative platforms (Runway, Descript, Midjourney) combined with Material Design principles for complex workflows.

**Key Principles:**
- Professional, cinematic aesthetic befitting high-end video production
- Clear information hierarchy for complex multi-step workflows
- Emphasis on visual feedback and progress states
- Production-focused dashboard mindset

## Typography

**Font Stack:**
- Primary: Inter (via Google Fonts CDN) - clean, modern, excellent readability
- Display/Headers: Space Grotesk - bold, confident for episode titles and hero sections
- Code/Technical: JetBrains Mono - for AI agent status and technical details

**Type Scale:**
- Display (Hero): text-5xl to text-7xl, font-bold
- Page Headers: text-3xl to text-4xl, font-semibold
- Section Headers: text-xl to text-2xl, font-semibold
- Body: text-base, font-normal
- Captions/Meta: text-sm, font-medium

## Layout System

**Spacing Primitives:** Use Tailwind units of 2, 4, 6, 8, 12, 16, 20, 24 for consistent rhythm
- Tight spacing: gap-2, p-4
- Standard spacing: gap-4, p-6, p-8
- Generous spacing: gap-8, p-12, p-16
- Section breaks: mt-20, mb-24

**Container Strategy:**
- Dashboard layout: max-w-full with sidebar navigation
- Content areas: max-w-7xl mx-auto
- Forms: max-w-2xl
- Modals: max-w-4xl

## Core Layout Structure

**Main Navigation:**
Persistent left sidebar (w-64) with:
- App logo/branding at top
- Primary navigation items with icons: Dashboard, New Episode, Library, Cast Manager, AI Agents, Settings
- User profile at bottom
- Collapsible for mobile (hamburger menu)

**Dashboard Layout:**
Multi-panel production workspace:
- Top bar: Global actions, notifications, user menu (h-16)
- Main content area: Grid-based dashboard cards
- Right panel (optional): AI agent activity feed (w-80)

## Component Library

### 1. Cast Member Cards
- Large format cards (aspect ratio 3:4) with profile photos
- Overlay gradient for name/role text
- Expandable detail view with personality traits, backstories
- Grid layout: grid-cols-2 md:grid-cols-3 lg:grid-cols-4

### 2. Episode Creation Wizard
Multi-step form with progress indicator:
- Step 1: Cast Selection (checkbox grid of cast members)
- Step 2: Storyline Input (large textarea with AI suggestions sidebar)
- Step 3: Episode Settings (duration, tone, conflict level)
- Step 4: Review & Generate
- Sticky bottom bar with Back/Next/Generate buttons

### 3. AI Agent Status Dashboard
Real-time production monitor:
- Agent cards showing: Script Writer, Voice Synthesizer, Video Producer, Editor, Marketing Bot
- Each card displays: Status badge, progress bar, current task, estimated time
- Visual hierarchy: Active agents highlighted, completed agents dimmed

### 4. Video Player & Preview
Cinematic player component:
- 16:9 aspect ratio container
- Custom controls: Play/pause, timeline scrubber, volume, fullscreen
- Thumbnail preview on hover
- Quality selector (if applicable)
- Scene markers on timeline

### 5. Episode Library
Netflix-style browsing interface:
- Horizontal scrolling rows by category: "Recent Episodes", "Trending", "By Cast"
- Large thumbnail cards (16:9) with episode title, duration, generation date
- Hover state: Subtle scale up, play icon overlay
- Grid fallback for "View All"

### 6. Production Dashboard Cards
Glassmorphic card design:
- Rounded corners (rounded-xl)
- Subtle borders
- Stats cards: Large number (text-4xl), label (text-sm), trend indicator
- Quick action cards with icon, title, description, CTA button

### 7. Form Inputs
Material Design inspired:
- Floating labels
- Bottom border focus state
- Helper text below inputs
- File upload: Drag-and-drop zone with preview grid

## Navigation Patterns

**Primary Navigation:** Fixed left sidebar
**Secondary Navigation:** Tabs within content areas (Episode types, Cast categories)
**Breadcrumbs:** For nested views (Library > Season 1 > Episode 3)

## Responsive Behavior

**Desktop (lg and up):** Full sidebar + multi-column layouts
**Tablet (md):** Collapsible sidebar + 2-column grids
**Mobile (base):** Hidden sidebar (hamburger), single column, stacked cards

## Animation Guidelines

**Use sparingly:**
- Loading states: Skeleton screens with shimmer effect
- Agent activity: Subtle pulse on active agents
- Progress bars: Smooth width transitions
- Page transitions: None (instant)
- Card hover: Minimal scale (scale-[1.02])

## Images

**Hero Section:** None - this is a production dashboard, not a marketing site
**Cast Member Profiles:** User-uploaded photos (placeholder: silhouette icons)
**Episode Thumbnails:** Generated video thumbnails (placeholder: generic gradient with episode number)
**Background:** Abstract gradient mesh or subtle grid pattern for main dashboard area
**Empty States:** Custom illustrations for "No episodes yet", "Add cast members", etc.

## Key UI States

**Generation In Progress:**
- Animated progress bar
- Agent status cards updating in real-time
- "Cancel Generation" button prominently placed

**Success State:**
- Confetti animation (brief, 2 seconds)
- "Episode Ready" banner with preview thumbnail
- Share/Download/Watch actions

**Error State:**
- Clear error message with troubleshooting steps
- "Retry" and "Report Issue" buttons
- Error details collapsible section