# Website Updates - December 10, 2025

## Changes Completed

### 1. ✅ Featured Publications
**Added three publications as featured in specific order:**
1. MOCHA (featured_order: 1)
2. CALICO (featured_order: 2)  
3. PurpCode (featured_order: 3)

**Removed author lists from homepage featured publications:**
- Homepage now shows only title, venue, and year for featured publications
- Cleaner, more focused display

### 2. ✅ Publications Page Updates

**arXiv → Preprint:**
- Publications with `publisher: "arXiv"` now display as "Preprint"
- More professional terminology

**Removed DOI display:**
- DOI links are no longer shown on the publications page
- Cleaner interface with just the action buttons

### 3. ✅ Publication Layout - Image Left (33% / 67% Split)

**Desktop layout:**
- Publication image: 33.33% width on the left
- Publication content: 66.67% width on the right
- Side-by-side horizontal layout
- Minimum image height: 250px

**Mobile responsive:**
- Stacks vertically on screens < 768px
- Image at top, content below
- Full width for both sections

## Files Modified

### Data Files
- `_data/publications.yml`
  - Added `featured: true` to MOCHA, CALICO, PurpCode
  - Added `featured_order` field (1, 2, 3) to control display order

### Page Templates
- `_pages/about.md` (Homepage)
  - Removed author list from featured publications
  - Added sorting by `featured_order`
  - Changed to show `pub.publisher` instead of authors

- `_pages/publications.md`
  - Added logic to replace "arXiv" with "Preprint"
  - Removed DOI display section

### Styles
- `_sass/_modern.scss`
  - Changed `.publication-item` to `flex-direction: row`
  - Set `.pub-image-large` to `width: 33.33%`
  - Set `.pub-content-main` to `width: 66.67%`
  - Added responsive styles for mobile (vertical stacking)

## Visual Changes

### Homepage Featured Publications
**Before:**
```
[Image]
Title
Authors list
Venue • Year
[Buttons]
```

**After:**
```
[Image]
Title
Venue • Year
[Buttons]
```

### Publications Page

**Layout Before:**
```
┌─────────────────────┐
│                     │
│  Image (full width) │
│                     │
├─────────────────────┤
│   Content           │
└─────────────────────┘
```

**Layout After (Desktop):**
```
┌──────────┬─────────────────────────┐
│          │  Title                  │
│  Image   │  Authors                │
│  (33%)   │  Preprint • 2025        │
│          │  [Buttons]              │
└──────────┴─────────────────────────┘
        67% content →
```

**Venue Display:**
- "arXiv" → "Preprint"
- Other venues shown as-is

**Removed:**
- DOI links at the end of each publication

## Featured Publications Order

The three featured publications will appear in this order on the homepage:

1. **MOCHA**: Are Code Language Models Robust Against Multi-Turn Malicious Coding Prompts?
   - EMNLP Findings • 2025

2. **CALICO**: Part-Focused Semantic Co-Segmentation with Large Vision-Language Models
   - CVPR • 2025

3. **PurpCode**: Reasoning for Safer Code Generation
   - NeurIPS • 2025

## Testing

To test your changes locally:
```powershell
bundle exec jekyll serve
```

Then visit:
- Homepage: http://localhost:4000/
- Publications: http://localhost:4000/publications/

Check:
- ✅ Featured publications show in correct order (MOCHA, CALICO, PurpCode)
- ✅ No author lists on homepage featured publications
- ✅ arXiv publications show as "Preprint"
- ✅ No DOI displayed on publications page
- ✅ Publication images on left (33%), content on right (67%)
- ✅ Mobile view stacks vertically

## Notes

- The `featured_order` field controls the display sequence on the homepage
- Publications page sorts by date (newest first) regardless of featured status
- Image layout is responsive and adapts to screen size
- All featured publications automatically appear on the homepage
