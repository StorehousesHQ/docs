# Mintlify documentation

## Project overview
- **App**: Storehouses - Alternative asset portfolio management platform
- **Description**: Track and manage precious metals, watches, gems, jewelry, wine, spirits, fine art, arms & armor, and other valuable collectibles
- **Live site**: https://storehouses.app
- **Docs site**: https://docs.storehouses.app
- **Source code**: ./app-source

## App discovery workflow
When generating or updating documentation:
1. **Check the live site** - Visit https://storehouses.app to understand current UI, navigation, and user flows
2. **Reference source code** - Look at the app codebase for:
   - Route definitions (to understand page structure)
   - Widget/component files (to understand features)
   - API integrations (to document data flows)
   - State management (to understand app behavior)
3. **Cross-reference** - Ensure docs match actual app behavior

## Source code locations (storehouses-docs repo has a symlink to storehouses repo, where the code is, at ./app-source)
- App repo: `./app-source/`
- App routes (Next.js App Router): `./app-source/src/app/`
- Components: `./app-source/src/components/`
- Server actions: `./app-source/src/actions/`
- API routes: `./app-source/src/app/api/`
- Utilities: `./app-source/src/utils/`
- Database schema: `./app-source/supabase/migrations/`
- Email templates: `./app-source/src/emails/`
- React hooks: `./app-source/src/hooks/`

## Key app sections to document
- **Dashboard** - Portfolio overview with value charts and allocation breakdowns
- **Items** - Add, view, edit, and manage individual assets (precious metals, watches, gems, jewelry, wine, spirits, fine art, arms & armor)
- **Collections** - Organize items into custom collections
- **Locations** - Track physical storage locations for items
- **Alerts** - Set up price alerts for precious metals and other assets
- **Heir Access** - Emergency access system for designated heirs
- **Export** - Export portfolio data to PDF, CSV, or print
- **Sharing** - Share portfolio views with others via secure links
- **Account Settings** - Manage profile, email, password, and account preferences
- **Billing & Subscription** - Manage subscription tiers (free, pro, lifetime)
- **Wealth Garden** - Visualization of portfolio growth over time
- **Offline Mode** - PWA functionality for offline access

## Working relationship
- You can push back on ideas - this can lead to better documentation
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up information
- When documenting a feature, verify it exists in the source code first

## Project context
- Format: MDX files with YAML frontmatter
- Config: docs.json for navigation, theme, settings
- Components: Mintlify components

## Content strategy
- Document just enough for user success - not too much, not too little
- Prioritize accuracy and usability of information
- Make content evergreen when possible
- Search for existing information before adding new content
- Check existing patterns for consistency
- Start by making the smallest reasonable changes

## Frontmatter requirements for pages
- title: Clear, descriptive page title
- description: Concise summary for SEO/navigation

## Writing standards
- Second-person voice ("you")
- Prerequisites at start of procedural content
- Test all code examples before publishing
- Match style and formatting of existing pages
- Include both basic and advanced use cases
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links

## Git workflow
- NEVER use --no-verify when committing
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists
- Commit frequently throughout development
- NEVER skip or disable pre-commit hooks

## Do not
- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Include untested code examples
- Document features that don't exist in the app
- Make assumptions - always ask for clarification

## Tech stack context
- **Framework**: Next.js 16 with App Router
- **Language**: JavaScript/JSX (React 19)
- **Styling**: Tailwind CSS 4
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth
- **Payments**: Stripe
- **Email**: Resend
- **Charts**: Recharts
- **PWA**: Serwist (service worker)
- **State**: React hooks and server actions
- **Analytics**: Custom analytics with Intercom integration

## Key data models
- **Items** - Core asset records with category-specific metadata tables:
  - `precious_metals` - Gold, silver, platinum, palladium, rhodium with weight, purity, spot prices
  - `watches` - Brand, model, reference number, movement, case material
  - `gems` - Gem type, carat weight, cut, color, clarity
  - `wine` - Vintage, region, producer, varietal
  - `spirits` - Type, age, distillery, ABV
  - `jewelry` - Materials, stones, designer
  - `fine_art` - Artist, medium, dimensions, provenance
  - `arms_armor` - Type, era, manufacturer, condition
- **Collections** - User-created groups of items
- **Locations** - Physical storage locations with custom/preset options
- **Alerts** - Price monitoring for assets with notification preferences
- **Heir Access** - Emergency access configuration with designated contacts
- **Share Links** - Temporary or permanent portfolio sharing
- **Subscriptions** - User tier management (free, pro, lifetime)
