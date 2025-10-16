# For Mitre Media

## Javascript

I’d rate my JavaScript understanding as 6 out of 10.

I have solid command of modern syntax and modular patterns. I’m comfortable destructuring data and handling DOM interactions, but I’m still deepening my knowledge.

One example that reflects my practical understanding is how I isolated a utility function in the Eos project. Its objective is to merge conditional class names for components, improving consistency and readability across the codebase.

````
export const cn = (...classes: (string | undefined | null | false)[]) =>
  classes.filter(Boolean).join(" ");
````

It is a small pattern of reusable code that avoids duplication and improves clarity. I aim to keep evolving from this practical fluency toward deeper insights into runtime behavior and optimization.

## SQL queries

I’d rate my SQL proficiency as 7 out of 10. I use SQL daily through ActiveRecord and Arel, reviewing generated queries to ensure performance and scalability. My goal is always to write expressive and efficient statements that keep database load scalable.

At Liber Capital, I often dealt with N+1 query issues in financial APIs. Some endpoints would trigger dozens of redundant SQL calls when fetching model instances and their associated objects. I analyzed these cases and optimized them through eager loading with includes and preload.

````
# Before example
Invoice.all.map { |i| i.payments.count }

# Before example
Invoice.joins(:payments).count

# After
Invoice.includes(:payments).count
````

Also, to prevent regressions, I implemented the Bullet gem in our staging and test environments. It automatically flagged inefficient queries and unused eager loads during development.


## Database optimization

I’d rate my understanding of database optimization as 7 out of 10. I work daily with PostgreSQL and focus on designing schemas and queries that remain performant as data scales. My approach combines proper indexing, caching, and query plan analysis.

At Liber Capital, we maintained a high-volume financial platform where some endpoints became slow due to unoptimized joins and missing indexes. I used the `.explain` method in rails to identify sequential scans on critical models and added composite indexes on high-selectivity columns such as (invoice_id, status) and (invoice_id, due_date).

These adjustments reduced query times from several seconds to under 200 ms on frequently accessed reports.
I also introduced query caching for repeated aggregations and background precomputation for dashboards, balancing read/write performance.

## CSS

I’d rate my CSS understanding as 7 out of 10. My focus is on building scalable and consistent visual systems rather than isolated styles. I’m comfortable with modern CSS (Flexbox, Grid, variables, and responsive layouts) and I typically use frameworks like Tailwind to enforce structure and maintain visual harmony.

In my personal project Sereni, I built a small design system from scratch using design tokens to define spacing, typography, and color palettes. These tokens were mapped to Tailwind utilities, creating a single source of truth for the entire visual identity. Doing so ensured consistency across components and made it easier to evolve the brand without rewriting styles.

This experience deepened my understanding of CSS as a system, how small, well-structured rules and clear conventions can make large interfaces easier to scale and maintain.

## Ruby
I’d rate my Ruby expertise as 8 out of 10. I love Ruby’s expressiveness and its ability to turn complex logic into readable, maintainable code. I focus on designing clean abstractions that keep business logic isolated and easy to reason about.

A good example was building service objects to handle external API integrations. Instead of spreading HTTP calls and error handling across models or controllers, I created dedicated classes that encapsulated authentication, request formatting, and response parsing.

This approach reduced coupling, simplified testing, and made it easier to swap integrations without touching core business code.
That’s what I value most about Ruby, it allows for simplicity and elegance.

## Rails
I’d rate my Rails expertise as 8 out of 10. I’ve spent most of my career building and scaling Rails applications, with a strong focus on clean architecture, performance, and maintainability. I understand how Rails components (ActiveRecord, ActiveSupport, ActionPack, etc.) work together and how to structure large systems for clarity and reuse.

At Liber Capital, I led a major refactor to improve the organization of our models, which had grown overly large and with duplicated logic across the codebase. I introduced a modular structure using Rails concerns such as `Billable`, `Notifiable`, and `Auditable` to encapsulate business behaviors, and `HasLimits` and `HasAddress` for cross-cutting functionality.

This restructuring reduced model size significantly, improved test coverage, and made new features easier to extend without breaking existing logic. It also fostered a culture of DRY, well-defined boundaries within our domain models.

That experience reinforced why I enjoy working with Rails, its conventions and flexibility allow for fast delivery without sacrificing maintainability.