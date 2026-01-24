# Example Workflows

Real scenarios showing how to use OpenTrace with your AI assistant.

## Investigating a Production Incident

You're paged about checkout failures. Here's how to investigate:

**1. Understand what's involved**

> "What services are involved in the checkout flow?"

The AI maps out the services: `checkout-api` → `inventory-service` → `payment-processor` → `order-service`

**2. Check dependencies**

> "What does checkout-api depend on?"

You see it depends on `auth-service`, `inventory-service`, `payment-processor`, and `redis-cache`.

**3. Trace the failure path**

> "If inventory-service is slow, what would be affected?"

The AI shows you the blast radius - checkout, order confirmation, and inventory sync would all be impacted.

**4. Find the connection**

> "How does checkout-api connect to the database?"

You see the path goes through `order-service` which connects to `postgres-main`.

---

## Understanding a Service Before Making Changes

You need to modify the notification service. Start by understanding its role:

**1. Get the overview**

> "Tell me about the notification-service"

**2. Find what depends on it**

> "What services call notification-service?"

You discover 12 services send notifications through it - more than you expected.

**3. Check what it needs**

> "What does notification-service depend on?"

It depends on `email-gateway`, `sms-provider`, `push-notification-service`, and `user-preferences-api`.

**4. Assess the risk**

> "How critical is notification-service to the system?"

The AI analyzes its connectivity and tells you it's a high-traffic service with many consumers.

---

## Onboarding to a New Codebase

You just joined the team. Get up to speed quickly:

**1. See the landscape**

> "What services are in my system?"

**2. Find the core services**

> "What are the most connected services?"

The AI identifies the key services that everything depends on.

**3. Understand groupings**

> "What services handle payments?"

> "What services handle user management?"

**4. Trace a user journey**

> "How does a request flow from the mobile app to the order database?"

---

## Planning a Service Deprecation

You need to retire the legacy-auth service:

**1. Find all consumers**

> "What services depend on legacy-auth?"

You get a list of everything that needs to be migrated.

**2. Check for indirect dependencies**

> "Are there services that indirectly depend on legacy-auth?"

The AI traces deeper connections you might have missed.

**3. Understand the migration scope**

> "What's the difference between what calls legacy-auth vs new-auth-service?"

**4. Verify nothing is missed**

> "Is there anything else connected to legacy-auth?"

---

## Debugging Performance Issues

The API is slow. Figure out why:

**1. Map the request path**

> "Show me the path from api-gateway to the response"

**2. Identify bottlenecks**

> "What databases does the user-profile endpoint touch?"

**3. Find shared dependencies**

> "What do api-gateway, user-service, and order-service all depend on?"

You discover they all share a connection to a cache that might be the bottleneck.

**4. Check for cascading issues**

> "If redis-cache is slow, what services would be affected?"
