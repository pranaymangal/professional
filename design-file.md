So while creating a website, what kind of systems do you think, what kind of like design systems do you think one follows? What are the best practices? Do you go through the blogs of famous tech websites or, you know, these tech websites or for like developers' blogs which talk about the best libraries or like design principles which should be used, which converts the user easily, you know, which is fast and, you know, I don't need to tell you what are the essential requirements when we make a website, right? So yeah, it should be proper. So if I, I want to have a list of all those like design systems or like resources so that I can feed it into an AI agent and then the AI agent will take care of all of this while it is creating the websites through the prompt and I will save it into the skills of the AI and yeah.
Edit
Copy
Share
Curated List of Design CSS and Performance Resources
If you're building an AI agent that needs to generate production-ready websites, you need to feed it a curated stack rather than just random libraries. Here's a structured knowledge base that covers design systems, performance constraints, and conversion psychology—organized as "skills" you can inject into your agent's context:
1. Core Design System Architecture
Atomic Design Methodology
Atoms (buttons, inputs, labels) → Molecules (search bars) → Organisms (headers) → Templates → Pages
Reference: Brad Frost's Atomic Design book + atomicdesign.bradfrost.com
Token-Based Design Systems (Critical for AI consistency)
Style Dictionary by Amazon (transforms design tokens across platforms)
Tokens Studio for Figma-to-code pipelines
Variables: Colors (primitive/semantic), Typography scales (major third/perfect fourth), Spacing (4px/8px base grids), Elevation (shadows/z-index), Motion (duration/easing curves)
2. Component Libraries & Implementation Standards
Headless First (Accessibility + Customization)
Radix UI (primitives: Dialog, Dropdown, Tabs—unstyled, fully accessible)
Headless UI by Tailwind Labs
React Aria by Adobe (robust accessibility hooks)
Opinionated Systems (Faster deployment)
shadcn/ui (Tailwind + Radix, copy-paste components, currently the industry favorite)
Material Design 3 (Google's latest with dynamic color/material you)
Ant Design (enterprise/dashboard heavy, excellent for B2B tools)
Chakra UI (if you need style props approach)
Carbon Design System (IBM's enterprise-grade, excellent for data-heavy apps)
The "Vercel Aesthetic" (What modern devs actually use)
Tailwind CSS (utility-first)
Lucide React (icons)
Framer Motion (micro-interactions)
Geist or Inter font families
3. Performance & Technical Constraints (Hard Rules)
Core Web Vitals Thresholds (Your agent must know these limits)
LCP (Largest Contentful Paint): <2.5s
INP (Interaction to Next Paint): <200ms (replaces FID in 2024)
CLS (Cumulative Layout Shift): <0.1
TTFB (Time to First Byte): <600ms
Resource Loading Strategy
Next.js 14+ App Router (Server Components by default)
Images: WebP/AVIF, explicit width/height, lazy loading below fold
Fonts: next/font or font-display: swap
Third-party scripts: Partytown or web workers for analytics
Accessibility Non-Negotiables
WCAG 2.1 AA compliance minimum
Keyboard navigation (Tab order, Escape to close modals)
ARIA labels for dynamic content
Color contrast 4.5:1 for normal text, 3:1 for large text
Focus visible states (never remove outlines without replacement)
4. Conversion & UX Psychology
Cognitive Load Reduction
Hick's Law: Minimize choices in navigation (max 7±2 items)
Fitts's Law: Touch targets minimum 44x44px, primary actions closer to thumb zones on mobile
Miller's Law: Chunk information into groups of 5-9 items
Visual Hierarchy Patterns
Z-Pattern (Landing pages): Logo → Hero → CTA → Trust signals
F-Pattern (Content heavy): Left-aligned, scannable headings
Layered Architecture: Background → Content → Floating Elements (CTAs, chat widgets)
Trust Signals
Social proof placement (above fold or near CTAs)
Security badges at checkout/contact forms
Consistent spacing (8px grid system prevents "design feels off" issues)
5. Curated Resource Feeds for Your Agent
Technical Implementation Blogs
Vercel Engineering Blog (App Router patterns, edge functions)
Web.dev by Google (Core Web Vitals updates, CSS optimization)
Smashing Magazine (UX case studies, accessibility deep dives)
A List Apart (semantic HTML, progressive enhancement)
Design System Documentation (Reference architectures)
Polaris (Shopify) - E-commerce patterns
Spectrum (Adobe) - Creative tool interfaces
Lightning Design System (Salesforce) - Enterprise CRM patterns
Fluent UI (Microsoft) - Office 365 style productivity apps
Conversion Optimization
CXL Blog (data-driven UX)
Baymard Institute (e-commerce UX research—premium but gold standard)
GoodUI.org (A/B test patterns)
6. AI Agent "System Prompt" Structure
When you feed this to your agent, structure it as constraints:
Copy
ROLE: Senior Frontend Architect
CONSTRAINTS:
- Use Tailwind CSS with 8px spacing scale
- Implement Radix UI primitives for all interactive elements
- Ensure WCAG 2.1 AA compliance on color contrast
- Optimize images to <100KB with lazy loading
- Follow Next.js 14 App Router patterns
- Mobile-first responsive breakpoints (sm:640px, md:768px, lg:1024px)
- Loading states required for all async operations
- Error boundaries for all route segments

CONVERSION_RULES:
- Primary CTA uses high-contrast color (60-30-10 rule: 60% neutral, 30% secondary, 10% primary action)
- Form labels above inputs (not placeholders)
- Progress indicators for multi-step processes
- Sticky header on scroll with backdrop-blur
7. Anti-Patterns to Block
Make sure your agent knows what not to do:
No carousels for hero content (conversion killers, poor accessibility)
No infinite scroll without footer reveal option
No custom scrollbars that break native behavior
No layout shifts caused by late-loading fonts/images
No !important in CSS (indicates specificity issues)
No placeholder text as labels (accessibility fail)
Pro tip: Instead of feeding raw blog URLs, extract the design tokens and component APIs from these systems (like Material's token JSON or Tailwind's config schema) and feed those as structured data. AI agents work better with structured constraints than with unstructured blog text.
Would you like me to generate a specific "skill manifest" JSON format that you can directly import into your agent framework?
yes pls create a specific skill manifest in json format
Edit
Copy
Share
Generate Websites Using Precise Design Tokens and Component Standards
JSON
Copy
{
  "skill_manifest": {
    "metadata": {
      "name": "production_web_design_system",
      "version": "1.0.0",
      "description": "Comprehensive design system and architectural constraints for AI-generated production websites",
      "target_frameworks": ["nextjs", "react", "tailwindcss"],
      "priority": "high",
      "compliance_level": "WCAG_2.1_AA"
    },
    
    "design_tokens": {
      "colors": {
        "primitive": {
          "neutral": {
            "50": "#fafafa",
            "100": "#f5f5f5",
            "200": "#e5e5e5",
            "300": "#d4d4d4",
            "400": "#a3a3a3",
            "500": "#737373",
            "600": "#525252",
            "700": "#404040",
            "800": "#262626",
            "900": "#171717",
            "950": "#0a0a0a"
          },
          "brand": {
            "primary": "#0f172a",
            "accent": "#3b82f6",
            "destructive": "#ef4444",
            "success": "#22c55e",
            "warning": "#f59e0b"
          }
        },
        "semantic": {
          "background": "$neutral.50",
          "foreground": "$neutral.900",
          "muted": "$neutral.100",
          "border": "$neutral.200",
          "primary": "$brand.primary",
          "primary_foreground": "#ffffff",
          "ring": "$brand.accent",
          "card": "#ffffff",
          "popover": "#ffffff"
        }
      },
      
      "typography": {
        "font_family": {
          "sans": ["Inter", "system-ui", "sans-serif"],
          "mono": ["JetBrains Mono", "monospace"],
          "display": ["Inter", "system-ui", "sans-serif"]
        },
        "scale": {
          "xs": "0.75rem",
          "sm": "0.875rem",
          "base": "1rem",
          "lg": "1.125rem",
          "xl": "1.25rem",
          "2xl": "1.5rem",
          "3xl": "1.875rem",
          "4xl": "2.25rem",
          "5xl": "3rem"
        },
        "line_height": {
          "tight": "1.25",
          "normal": "1.5",
          "relaxed": "1.625"
        },
        "font_weight": {
          "normal": "400",
          "medium": "500",
          "semibold": "600",
          "bold": "700"
        }
      },
      
      "spacing": {
        "base_unit": "0.25rem",
        "scale": [0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16, 20, 24, 32, 40, 48, 64],
        "section_padding": {
          "mobile": "3rem",
          "tablet": "5rem",
          "desktop": "8rem"
        }
      },
      
      "elevation": {
        "shadows": {
          "sm": "0 1px 2px 0 rgb(0 0 0 / 0.05)",
          "md": "0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)",
          "lg": "0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1)",
          "xl": "0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1)"
        },
        "border_radius": {
          "sm": "0.375rem",
          "md": "0.5rem",
          "lg": "0.75rem",
          "xl": "1rem",
          "full": "9999px"
        }
      },
      
      "motion": {
        "easing": {
          "default": "cubic-bezier(0.4, 0, 0.2, 1)",
          "in": "cubic-bezier(0.4, 0, 1, 1)",
          "out": "cubic-bezier(0, 0, 0.2, 1)",
          "bounce": "cubic-bezier(0.68, -0.55, 0.265, 1.55)"
        },
        "duration": {
          "fast": "150ms",
          "normal": "250ms",
          "slow": "350ms"
        },
        "performance": {
          "use_transform": true,
          "use_opacity": true,
          "avoid_layout_properties": ["width", "height", "top", "left", "margin", "padding"]
        }
      },
      
      "breakpoints": {
        "sm": "640px",
        "md": "768px",
        "lg": "1024px",
        "xl": "1280px",
        "2xl": "1536px"
      }
    },
    
    "tech_stack": {
      "framework": {
        "primary": "nextjs",
        "version": "14+",
        "features": ["app_router", "server_components", "parallel_routes", "interception_routes"]
      },
      "styling": {
        "primary": "tailwindcss",
        "version": "3.4+",
        "config": {
          "dark_mode": "class",
          "content": ["./app/**/*.{js,ts,jsx,tsx}", "./components/**/*.{js,ts,jsx,tsx}"]
        }
      },
      "ui_primitives": {
        "library": "radix_ui",
        "components": ["dialog", "dropdown-menu", "accordion", "tabs", "tooltip", "popover", "slider", "switch"]
      },
      "component_library": {
        "primary": "shadcn_ui",
        "installation_method": "cli",
        "base_color": "neutral"
      },
      "animation": {
        "library": "framer_motion",
        "use_for": ["page_transitions", "gestures", "layout_animations", "micro_interactions"],
        "avoid_for": ["scroll_animations"]
      },
      "icons": {
        "library": "lucide_react",
        "size_scale": [16, 20, 24, 32, 48]
      },
      "fonts": {
        "loading_strategy": "next_font",
        "optimization": true,
        "display": "swap"
      }
    },
    
    "component_standards": {
      "button": {
        "accessibility": {
          "min_touch_target": "44px",
          "focus_ring": "2px solid $brand.accent",
          "focus_ring_offset": "2px"
        },
        "variants": {
          "primary": {
            "bg": "$brand.primary",
            "color": "$primary_foreground",
            "hover_brightness": "1.1"
          },
          "secondary": {
            "bg": "$neutral.100",
            "color": "$neutral.900"
          },
          "ghost": {
            "bg": "transparent",
            "hover_bg": "$neutral.100"
          }
        },
        "sizes": {
          "sm": "h-9 px-3",
          "md": "h-10 px-4",
          "lg": "h-11 px-8",
          "icon": "h-10 w-10"
        }
      },
      
      "input": {
        "accessibility": {
          "label_position": "above",
          "placeholder_usage": "optional_hint_only",
          "error_association": "aria_describedby",
          "min_touch_target": "44px"
        },
        "states": {
          "focus": "ring-2 ring-$brand.accent border-$brand.accent",
          "error": "border-$brand.destructive focus:ring-$brand.destructive",
          "disabled": "opacity-50 cursor-not-allowed"
        }
      },
      
      "card": {
        "structure": {
          "padding": "$spacing.6",
          "border_radius": "$border_radius.lg",
          "background": "$colors.semantic.card",
          "shadow": "$elevation.shadows.md"
        },
        "elements": {
          "header": "flex flex-col space-y-1.5 p-6",
          "content": "p-6 pt-0",
          "footer": "flex items-center p-6 pt-0"
        }
      },
      
      "navigation": {
        "patterns": {
          "max_items": 7,
          "mobile": "sheet_dropdown",
          "desktop": "horizontal_bar",
          "sticky_behavior": {
            "trigger": "scroll_50px",
            "style": "backdrop_blur_md bg_background_80"
          }
        },
        "accessibility": {
          "skip_link": true,
          "current_page_indicator": "aria_current_page",
          "dropdown_keyboard": "arrow_navigation"
        }
      },
      
      "modal": {
        "accessibility": {
          "focus_trap": true,
          "escape_close": true,
          "click_outside_close": true,
          "aria_labelled_by": "title_id",
          "aria_described_by": "description_id"
        },
        "animation": {
          "enter": "fade_in scale_95",
          "exit": "fade_out scale_95",
          "duration": "$motion.duration.normal"
        }
      },
      
      "image": {
        "optimization": {
          "format": ["webp", "avif"],
          "fallback": "jpeg",
          "lazy_loading": "below_fold",
          "priority_loading": "above_fold_hero",
          "max_dimension": 1920,
          "quality": 85
        },
        "aspect_ratios": {
          "video": "16/9",
          "square": "1/1",
          "portrait": "3/4",
          "landscape": "4/3",
          "ultrawide": "21/9"
        }
      }
    },
    
    "performance_budgets": {
      "core_web_vitals": {
        "lcp": {
          "target": "2.5s",
          "maximum": "4.0s",
          "unit": "seconds"
        },
        "inp": {
          "target": "200ms",
          "maximum": "500ms",
          "unit": "milliseconds"
        },
        "cls": {
          "target": 0.1,
          "maximum": 0.25,
          "unit": "unitless"
        },
        "ttfb": {
          "target": "600ms",
          "maximum": "1.0s",
          "unit": "milliseconds"
        }
      },
      
      "resource_limits": {
        "javascript": {
          "initial_bundle": "150kb",
          "lazy_chunk_max": "100kb",
          "third_party_total": "250kb"
        },
        "css": {
          "critical_path": "50kb",
          "total": "100kb"
        },
        "images": {
          "hero_max": "200kb",
          "content_max": "100kb",
          "thumbnail_max": "50kb"
        },
        "fonts": {
          "max_variants": 3,
          "total_weight": "300kb",
          "font_display": "swap"
        }
      },
      
      "optimization_rules": {
        "images": {
          "responsive_sizing": true,
          "placeholder": "blur_up_or_color",
          "loading": "lazy_below_fold"
        },
        "scripts": {
          "strategy": "lazy_on_interaction",
          "third_party": "partytown_or_worker",
          "analytics_defer": true
        },
        "css": {
          "purge_unused": true,
          "critical_css_inline": true,
          "unused_removal": true
        }
      }
    },
    
    "accessibility_requirements": {
      "wcag_level": "AA",
      "mandatory_checks": [
        "color_contrast_4.5_1_text",
        "color_contrast_3_1_large_text",
        "keyboard_navigation_logical",
        "focus_visible_indicators",
        "aria_labels_interactive",
        "alt_text_images",
        "heading_hierarchy",
        "landmark_regions",
        "skip_navigation_link",
        "form_labels_associated",
        "error_identification",
        "resize_text_200_percent",
        "motion_respect_prefers_reduced_motion"
      ],
      
      "keyboard_navigation": {
        "tab_order": "logical_dom_order",
        "trap_focus_in_modals": true,
        "escape_closes_modals": true,
        "enter_activates_buttons": true,
        "space_activates_checkboxes": true,
        "arrow_keys_navigate_menus": true
      },
      
      "screen_reader": {
        "announce_dynamic_content": "aria_live_regions",
        "hide_decorative_elements": "aria_hidden",
        "describe_complex_graphics": "aria_labelledby_or_describedby",
        "status_messages": "role_status_or_alert"
      },
      
      "visual": {
        "focus_indicators": {
          "style": "solid_outline",
          "width": "2px",
          "offset": "2px",
          "color": "$brand.accent"
        },
        "text_resizing": "zoom_and_text_only",
        "line_height_minimum": 1.5,
        "letter_spacing_readable": "0.01em"
      }
    },
    
    "ux_conversion_patterns": {
      "cognitive_load": {
        "hicks_law": "max_7_navigation_items",
        "millers_law": "chunk_content_into_5_to_9_items",
        "fitts_law": {
          "touch_target_minimum": "44px",
          "primary_actions_large": "48px",
          "distance_to_targets": "minimize_travel_distance"
        }
      },
      
      "visual_hierarchy": {
        "z_pattern": "landing_pages_hero_cta",
        "f_pattern": "content_heavy_text_pages",
        "golden_triangle": "top_left_priority_content",
        "whitespace": "generous_margins_improve_comprehension"
      },
      
      "conversion_optimization": {
        "cta_placement": {
          "above_fold_primary": true,
          "sticky_header_cta": "on_scroll",
          "repeated_every_3_sections": "long_pages"
        },
        "form_optimization": {
          "max_fields_initial": 3,
          "progress_indicators": "multi_step",
          "inline_validation": "on_blur",
          "password_requirements": "visible_inline"
        },
        "trust_signals": {
          "security_badges": ["ssl", "payment_secure"],
          "social_proof": ["testimonials", "user_counts", "ratings"],
          "guarantees": ["money_back", "free_trial"]
        }
      },
      
      "mobile_specific": {
        "thumb_zone": "primary_actions_bottom_center",
        "input_zoom_prevention": "font_size_16px_minimum",
        "gesture_support": "swipe_carousels_optional",
        "bottom_sheet_modals": "instead_of_center_modals_on_mobile"
      }
    },
    
    "anti_patterns": {
      "strictly_prohibited": [
        {
          "pattern": "infinite_scroll_without_footer_access",
          "reason": "accessibility_and_seo_issues",
          "alternative": "load_more_button_or_pagination"
        },
        {
          "pattern": "carousel_as_hero_content",
          "reason": "low_engagement_poor_accessibility",
          "alternative": "static_hero_with_clear_cta"
        },
        {
          "pattern": "placeholder_text_as_labels",
          "reason": "accessibility_violation_usability",
          "alternative": "floating_labels_or_static_labels"
        },
        {
          "pattern": "custom_scrollbars_breaking_native",
          "reason": "usability_friction",
          "alternative": "native_scrollbars_with_css_styling_only"
        },
        {
          "pattern": "autoplay_video_with_sound",
          "reason": "ux_intrusion_accessibility",
          "alternative": "muted_autoplay_with_user_toggle"
        },
        {
          "pattern": "layout_shifts_during_load",
          "reason": "cls_violation",
          "alternative": "explicit_dimensions_containers"
        },
        {
          "pattern": "important_in_css",
          "reason": "specificity_debt_maintenance_issues",
          "alternative": "higher_specificity_selectors_or_cascade_layers"
        },
        {
          "pattern": "detecting_touch_for_layout",
          "reason": "unreliable_detection_breaks_desktop",
          "alternative": "feature_detection_and_responsive_design"
        }
      ],
      
      "code_smells": [
        "div_soup_instead_of_semantic_html",
        "onclick_handlers_without_keyboard_support",
        "missing_alt_attributes",
        "hardcoded_colors_instead_of_tokens",
        "magic_numbers_in_css",
        "inline_styles_except_critical_css",
        "synchronous_third_party_scripts_in_head"
      ]
    },
    
    "quality_gates": {
      "pre_deployment_checklist": [
        "lighthouse_score_above_90_all_categories",
        "validated_html_no_errors",
        "no_console_errors",
        "responsive_testing_320px_to_2560px",
        "keyboard_only_navigation_test",
        "screen_reader_test_nvda_or_vo",
        "color_contrast_checker_passed",
        "form_validation_functional",
        "404_page_customized",
        "meta_tags_complete",
        "favicon_present",
        "robots_txt_sitemap_xml"
      ],
      
      "design_review": [
        "consistent_spacing_8px_grid",
        "typography_hierarchy_clear",
        "color_usage_follows_semantic_tokens",
        "animation_respects_prefers_reduced_motion",
        "loading_states_defined",
        "error_states_defined",
        "empty_states_defined"
      ]
    }
  }
}