# CampusCart (showcase)

Public showcase for a private project. The source code is not published here.

CampusCart helps college students buy what they need for a semester: dorm essentials and required textbooks. Instead of searching retailer by retailer, the student picks a school, a dorm and their courses, and gets pre-filled cart links.

## The problem

Move-in and the first week of classes mean a lot of small purchases. Which items does this dorm actually need (air conditioning, kitchen, bed size)? Which edition of which textbook does the professor require? Where is it cheapest? Students answer this with group chats and a dozen browser tabs.

## How it works

1. **Dorm setup.** The student chooses a school and a residence hall, picks from required and optional products tailored to that hall, and gets cart links for the retailers.
2. **Textbooks.** The student imports a course schedule and gets the required materials for those courses, with price comparison across retailers.
3. **Bundles.** Shopping lists can be saved and reopened.
4. **Portals for staff.** Professors manage courses and upload syllabi. Resident advisors manage dorm info, policies and recommendations. Admins manage schools, dorms, products and users.

### Syllabus reading

A professor uploads a syllabus. The system finds the textbooks and materials in it and verifies each book before anything is saved:

- It only uses ISBNs that are actually printed in the syllabus. It does not guess.
- If an ISBN is missing or fails verification, it looks the book up by title and author and records where the ISBN came from (syllabus, looked up, corrected).
- Verified and unverified ISBNs look different, and an unverified one needs confirmation before it is saved.
- If a retailer has no offers for a book, it tries other editions of the same title.
- Only real retailer prices are shown, never placeholders.

## Status

MVP, started in November 2025. A working prototype, not a launched product. I am not claiming users or revenue.

## What is shown and what is kept private

This repository contains only this README. The source is private. I can walk through the product in a call or screen share.
