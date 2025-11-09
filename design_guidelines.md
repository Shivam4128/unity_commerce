# Unity Commerce Website Design Guidelines

## Design Approach

**Selected Approach:** Design System + B2B Reference Hybrid

Drawing inspiration from professional B2B platforms like Stripe, Shopify Partners, and AWS, combined with clean Material Design principles to convey trust, compliance, and international credibility. The design prioritizes clear information hierarchy, professional polish, and conversion-focused layouts suitable for export/trade industry.

---

## Typography System

**Font Families:**
- Primary: Inter (headings and UI elements) - Google Fonts
- Secondary: Source Sans Pro (body text) - Google Fonts

**Hierarchy:**
- H1 (Hero): text-5xl md:text-6xl lg:text-7xl, font-bold, leading-tight
- H2 (Section Titles): text-3xl md:text-4xl lg:text-5xl, font-bold
- H3 (Subsection): text-2xl md:text-3xl, font-semibold
- H4 (Card Titles): text-xl md:text-2xl, font-semibold
- Body Large: text-lg md:text-xl, font-normal, leading-relaxed
- Body Standard: text-base md:text-lg, leading-relaxed
- Small/Caption: text-sm md:text-base

---

## Layout & Spacing System

**Tailwind Spacing Units:** Consistently use 4, 6, 8, 12, 16, 20, 24, 32 units

**Container Widths:**
- Full-width sections: w-full with inner max-w-7xl mx-auto px-4 md:px-6 lg:px-8
- Content sections: max-w-6xl mx-auto
- Text-heavy sections: max-w-4xl mx-auto

**Vertical Rhythm:**
- Section padding: py-16 md:py-20 lg:py-32
- Component spacing: space-y-8 md:space-y-12
- Card/grid gaps: gap-6 md:gap-8 lg:gap-12

---

## Component Library

### Navigation
- Sticky header with shadow on scroll
- Logo left, navigation center/right
- "Explore Products" and "Partner With Us" CTAs
- Mobile: Hamburger menu with slide-in drawer
- Height: h-20

### Hero Section
- Full-width container with large hero image (Ayurvedic herbs, natural ingredients, or Indian agricultural landscape)
- Overlay with semi-transparent treatment for text readability
- Content: max-w-3xl, centered or left-aligned
- Two-button CTA group with primary + secondary styling
- Height: min-h-screen or h-[600px] md:h-[700px] lg:h-[800px]

### About Section
- Two-column layout on desktop (text + key highlights grid)
- Three-column grid for highlights (md:grid-cols-3)
- Each highlight: icon, bold title, supporting text

### Product Categories
- Four-card grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-4
- Card structure: Icon/illustration top, title, description, subtle hover lift
- Unified CTA below grid

### Certifications Section
- Centered content with max-w-4xl
- Icon grid: grid-cols-2 md:grid-cols-4, showcasing certification badges
- Each badge: logo placeholder, name, brief descriptor
- Trust tagline below

### Geographic Reach
- Visual world map graphic (use SVG map library or image)
- Country list in grid-cols-2 md:grid-cols-3 lg:grid-cols-4
- Each location: flag icon + country name

### Why Partner Section
- Five-item vertical list on mobile, grid-cols-1 md:grid-cols-2 lg:grid-cols-3 on desktop
- Each item: numbered badge, bold heading, 2-3 sentence description
- Alternating or staggered layout for visual interest

### Contact Form Section
- Two-column desktop layout: md:grid-cols-2 with gap-12
- Left: Google Form embed (iframe with responsive wrapper)
- Right: Company info, response time promise, contact details
- Full-width on mobile

### Footer
- Three-column layout: Company description | Quick links | Registration info
- Single column stack on mobile
- Bottom bar: Copyright and compliance note

---

## Form Elements
- Input fields: border, rounded-lg, p-4, focus states with ring
- Labels: text-sm font-medium, mb-2
- Textareas: min-h-32
- Submit button: Large, full-width on mobile, w-auto on desktop

---

## Images

**Required Images:**

1. **Hero Section** - Large, high-quality image (1920x1080 minimum)
   - Subject: Ayurvedic herbs in natural setting, Indian farm landscape, or botanical close-ups
   - Treatment: Full-width background with overlay for text contrast
   - Placement: Behind hero content with buttons using blurred backgrounds

2. **Product Category Cards** - Icon illustrations (not photos)
   - 4 custom icons representing: Raw Herbs, Powders, Extracts, Essential Oils
   - Style: Line art or minimal illustrations

3. **Geographic Map** - World map graphic
   - Highlight export destinations with pins or connection lines
   - Can use SVG map library

4. **Certification Logos** - APEDA, FSSAI, IEC, ISO badges
   - Official logos in grid format
   - Maintain aspect ratios

---

## Interaction Patterns

- **Smooth scroll** navigation between sections
- **Fade-in on scroll** for section content (use Intersection Observer)
- **Hover states** for cards: subtle lift (transform translateY(-4px)) and shadow increase
- **Button states** handle their own hover/active without custom implementation
- **Hero buttons** with blur background: backdrop-blur-md with semi-transparent background
- **Mobile menu** slide-in animation from right

---

## Grid & Card Systems

**Standard Card:**
- Rounded corners: rounded-xl
- Padding: p-6 md:p-8
- Shadow: shadow-sm hover:shadow-lg transition
- Border: Optional subtle border

**Product Category Grid:**
- Equal height cards
- Centered content alignment
- Consistent icon sizing at top

**Certification Grid:**
- Auto-fit layout with minimum card width
- Center-aligned badges
- Even spacing

---

## Google Form Integration

- Embed using iframe with responsive wrapper
- Container: aspect-ratio or min-h-[600px]
- Seamless integration with site styling via surrounding context
- Alternative: Direct form fields if Google Form styling conflicts with brand

---

This design creates a professional, trustworthy B2B export platform that emphasizes Unity Commerce's credibility, compliance, and international reach while maintaining visual appeal appropriate for the natural products industry.