# Almohtaref Company Website

**[Visit the live storefront](https://almohtaref-company-ui.pages.dev/)**

## Project overview

Almohtaref is a bilingual company website, product catalog, and administration dashboard for a supplier of computers, printers, surveillance systems, and networking equipment. The public website gives customers a place to explore products and services, compare specifications and prices, and prepare an order request. The administration dashboard lets company staff maintain the catalog, pricing, and website content through a dedicated application.

## Public website

| Feature | What customers can do |
| --- | --- |
| Product catalog | Browse categories, search the catalog, and filter products by the brands available in a category. |
| Product details | Review images, specifications, and pricing, then share a direct link to the product's detail page. |
| Language and currency | Switch between Arabic and English with right-to-left and left-to-right layouts, and display prices in US dollars (USD) or Syrian pounds (SYP). |
| Customer accounts | Register or sign in and save favorites and cart items to an account. |
| WhatsApp ordering | Review the cart and open a prefilled WhatsApp message with the selected products, quantities, and prices to send to the company. |
| Company information | Explore the company's services and business units, and find its contact details and social links. |

## Administration dashboard

- **Catalog management** — Create and edit products, categories, brands, and reusable specification definitions. Manage product images, display order, and visibility in the public catalog.
- **Pricing management** — Set regular and discounted prices in both currencies. Update SYP prices in bulk by entering an exchange rate and recalculating from the stored USD prices.
- **Website content** — Maintain services, business units, company information, contact settings, and social links through the dashboard.
- **Accounts and reporting** — Separate customer and administrator sign-in flows. Authorized staff can manage accounts and access website audience reports.

## Architecture and technology

| Layer | Technology and responsibility |
| --- | --- |
| Public website | Angular 22 and TypeScript. Renders the catalog, company pages, and customer shopping flows. |
| Administration dashboard | A separately deployable Angular application for catalog, content, pricing, and account management. |
| Shared frontend libraries | Nx workspace libraries for reusable UI components, design tokens, typed API clients, request and response models, and language and currency utilities. |
| Backend | ASP.NET Core on .NET 10. A REST API with separate interfaces for public browsing, customer actions, and administrator workflows. |
| Data layer | Entity Framework Core and SQL Server. Stores catalog data, product specifications, prices, accounts, carts, and favorites. |
| Public frontend hosting | Cloudflare Pages. |

The storefront and dashboard share components and API contracts, so changes to common controls and data types can be maintained centrally. The API handles business rules and authorization, including who can edit catalog records and which customer owns a cart or favorites list.

## Engineering highlights

- **Dual-currency pricing** — The database stores USD and SYP prices separately. The storefront displays the stored price for the selected currency. A bulk pricing action lets staff choose when to update SYP prices and which exchange rate to apply.
- **Catalog browsing and product links** — The category filter shows brands available for the selected category. Product detail pages use readable slugs, so customers can open and share a specific product directly. The catalog provides loading, empty, and retry states for data requests.
- **Bilingual interface** — The applications translate navigation, forms, and feedback, and adapt layout direction when switching languages. Shared controls keep those behaviors consistent across screens.
- **Catalog-based shopping assistant** — The project also includes an optional OpenAI-powered assistant that interprets questions in Arabic or English and recommends products from the catalog. Product facts such as prices, availability, and specifications come from catalog records. Deployment settings control availability, and server-side quotas limit usage.

## My contribution

I worked across the storefront, administration dashboard, REST API, and database. My work included building Angular product lists and detail pages, implementing category and brand filtering, and connecting management forms to typed API clients. I also worked on SQL Server catalog modeling, dual-currency pricing and bulk updates, and administrator account workflows.

## Source code

This repository presents the project as a portfolio case study. The application source code is maintained in private company repositories.
