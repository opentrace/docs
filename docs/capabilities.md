# What You Can Do

OpenTrace enables your AI assistant to answer questions about your system architecture. Here's what you can ask.

## Discover Your System

Find and learn about components in your architecture.

| You want to... | Ask something like... |
|----------------|----------------------|
| List all services | "What services exist in my system?" |
| Find a specific component | "Find the payment service" |
| Search by description | "Which services handle user authentication?" |
| Get component details | "Tell me about the order-processor service" |

## Understand Dependencies

Learn what your services depend on and what depends on them.

| You want to... | Ask something like... |
|----------------|----------------------|
| See what a service needs | "What does the checkout service depend on?" |
| Find consumers of a service | "What services call the notification API?" |
| Get full dependency picture | "Show me all dependencies for the user service" |
| Understand a component's role | "How critical is the cache service?" |

## Analyze Impact

Understand the blast radius of changes or failures.

| You want to... | Ask something like... |
|----------------|----------------------|
| Assess change impact | "What would be affected if I change the auth service?" |
| Plan for outages | "If the database goes down, what stops working?" |
| Evaluate risk | "How many services depend on the message queue?" |
| Find critical paths | "What are the most critical services in my system?" |

## Trace Connections

Understand how components connect through your system.

| You want to... | Ask something like... |
|----------------|----------------------|
| Find connection paths | "How does the mobile app connect to the database?" |
| Trace request flow | "Show me the path from API gateway to order fulfillment" |
| Understand data flow | "How does data get from user signup to the analytics service?" |

## Find Similar Components

Discover related or duplicate functionality.

| You want to... | Ask something like... |
|----------------|----------------------|
| Find similar services | "What services are similar to the email-sender?" |
| Identify duplicates | "Are there other services that do what payment-processor does?" |
| Group by function | "What services handle notifications?" |

## Investigate Issues

Get help during incidents and debugging.

| You want to... | Ask something like... |
|----------------|----------------------|
| Start an investigation | "Help me investigate why orders are failing" |
| Trace errors | "How might an error in auth-service affect checkout?" |
| Find root causes | "The payment page is slow - what services are involved?" |
| Review past investigations | "Show me recent investigations" |

## Tips for Better Results

**Be specific about what you're looking for:**

> "What does order-service depend on?" works better than "Tell me about dependencies"

**Name services as they appear in your system:**

> Use "user-auth-service" if that's the actual name, not just "auth"

**Ask follow-up questions:**

> Start with "What services exist?" then drill into "Tell me more about the payment service"
