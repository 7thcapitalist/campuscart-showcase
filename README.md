# CampusCart (showcase)

Public showcase for a private project. The source code is not published here.

CampusCart is a web app that helps college students buy what they need for a semester: dorm essentials and required textbooks. Instead of searching retailer by retailer, the student picks a school, a dorm and their courses, and gets pre-filled cart links.

## The problem

Move-in and the first week of classes mean a lot of small purchases. Which items does this dorm actually need (air conditioning, kitchen, bed size)? Which edition of which textbook does the professor require? Where is it cheapest? Students answer this with group chats and a dozen browser tabs.

## How it works

1. **Dorm setup.** The student chooses a school and a residence hall, picks from required and optional products tailored to that hall, and gets cart links for the retailers.
2. **Textbooks.** The student imports a course schedule and gets the required materials for those courses, with price comparison across retailers.
3. **Bundles.** Shopping lists can be saved and reopened.
4. **Portals for staff.** Professors manage courses and upload syllabus PDFs. Resident advisors manage dorm info, policies and recommendations. Admins manage schools, dorms, products and users.

### Syllabus parsing

A professor uploads a syllabus PDF. The text is extracted, a language model pulls out the textbooks and materials, and a verification step checks each ISBN against book databases before anything is saved.

Design notes:
- The model is told to include only ISBNs that are printed in the syllabus. It does not guess.
- If an ISBN is missing or fails the check digit, the system looks the book up by title and author through public book databases and records where the ISBN came from (syllabus, looked up, corrected).
- The UI shows verified and unverified ISBNs differently and asks for confirmation before saving an unverified one.
- When a retailer has no offers for a book's main ISBN, the system tries alternate editions of the same title, with a cap on attempts.
- Mock prices were removed. Only real prices from the retailer API are shown.

## Architecture

- Next.js App Router, with API routes as the backend
- PostgreSQL with Drizzle ORM (schools, dorms, courses, materials, products, bundles, books, retailer prices, cart snapshots)
- Session-based auth with four roles: student, professor, RA, admin
- A sourcing layer that fetches retailer prices and builds affiliate cart links
- An admin and moderation flow for changes submitted from the portals

## Stack

Next.js 15, React 19, TypeScript, Tailwind CSS, shadcn/ui (Radix), PostgreSQL, Drizzle ORM, OpenAI API for syllabus extraction, a textbook price API, Amazon Product Advertising API (optional).

## Status

MVP. Started in November 2025; most recent work in February 2026. Built on Replit. It is a working prototype, not a launched product, and I am not claiming users or revenue.

## What is shown and what is kept private

This repository contains only this README. The source is private because it was built fast, includes admin and migration utilities, and its git history has not been cleaned for publication. I can walk through the code in a call or screen share.
