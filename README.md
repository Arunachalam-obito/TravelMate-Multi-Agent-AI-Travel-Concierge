# TravelMate-Multi-Agent-AI-Travel-Concierge
Automatically plans trips, builds itineraries, recommends options, syncs calendars, and drafts booking emails using a multi-agent system.
TravelMate — Multi-Agent Travel Concierge

1. Problem Statement

Planning travel requires juggling many tasks: picking dates, comparing destinations, browsing hotels, reading local guides, drafting booking messages, and adding everything to your calendar. Most people spend hours researching options, checking availability, and organizing their plans manually.

This becomes even more time-consuming for students, families, frequent travelers, and professionals planning logistics-heavy trips.

The goal: eliminate repetitive travel-planning work while keeping the human in control of important decisions.

2. Solution Overview

TravelMate is a multi-agent travel concierge that automates the hardest parts of planning a trip. It converts a simple natural-language request—like “Plan a 3-day trip to Chennai within a ₹20,000 budget”—into a structured workflow handled by specialized agents:

Planner Agent: understands the request, breaks it into actionable steps.

Search Agent: gathers flight/hotel/activity options using search tools or local KB.

Itinerary Agent: generates a clean, day-by-day schedule.

Calendar Agent: creates events or checks conflicts.

Booking Agent: drafts booking emails/messages safely (never sends automatically).

All agents are orchestrated by a controller that enforces safety (confirmation required for critical actions), handles memory, and logs step-by-step operations for debugging and observability.

TravelMate saves users time and reduces planning friction while enabling personalization through memory and user preferences.

3. Key Features
✔ Multi-Agent Architecture

TravelMate uses a structured system of coordinated agents:

Planner Agent — takes user input and generates a JSON plan.

Search Agent — retrieves flights, hotels, local attractions.

Itinerary Agent — builds structured itineraries.

Calendar Agent — checks/creates events.

Booking Agent — drafts emails for reservations.

Agents operate sequentially or in parallel, depending on the task.

✔ Tools & Integrations

TravelMate demonstrates tool use by integrating multiple categories:

Web Search Tool (stub/mock for Kaggle safety)

Vector Knowledge Base (FAISS)

Calendar Tool (create/read events)

Email Drafting Tool

Custom Travel Info Tool

OpenAPI-compatible tool adapter

These tools are used automatically when required by the Planner Agent’s decomposition.

✔ Memory (Short-term + Long-term)

Session Memory: remembers context during conversation.

Long-term Memory (SQLite): stores traveler preferences such as:

preferred flight times

preferred hotels (budget vs luxury)

dietary requirements

trip history

frequently visited cities

This allows more personalized itineraries.

✔ Observability & Logging

The system logs:

agent plans

tool calls

results from tools

errors and retries

execution time per step

This helps evaluate planning quality and correctness.

✔ Evaluation

A 50-case evaluation dataset tests:

itinerary quality

planner decomposition correctness

tool selection accuracy

ability to detect date conflicts

budget-constrained recommendations

multi-day trips

multi-city plans

safety checks for booking operations

The agent achieves >80% correctness on structured-planning tasks.

✔ Safety

TravelMate never auto-books or auto-sends emails.
For actions like:

booking

sending emails

adding calendar events
The system asks for human confirmation.

4. Architecture Diagram (Text form for Kaggle)
