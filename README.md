Luxury Car Dealership Workflow Overview

📱 1. WhatsApp Trigger

The workflow begins when a customer sends a message on WhatsApp.
This message can be:

 Text

 Voice Note


This trigger activates the entire automation system for customer support.

🔀 2. Switch Node — Determine Message Type

The Switch node is used to determine the message type.

If the customer sends text, the workflow sends it directly to the Edit Fields node.

If the customer sends audio, it goes to Download Media for voice processing.

This step helps the system decide which path to follow.

⬇️ 3. Download Media

This node retrieves the audio file link from WhatsApp.

✔ WhatsApp never sends the actual audio
✔ It only sends a media URL
✔ Without this link, you cannot download or process the audio

So Download Media is essential.

🌐 4. HTTP Request

The HTTP Request node:

Uses the URL from Download Media

Downloads the actual audio file

Makes it ready for transcription

Transcribe Audio cannot read a link — it needs a real audio file.

🎙️ 5. Transcribe Audio

This node converts the real audio file into text, because:

✔ AI understands text
❌ AI cannot understand raw audio

So voice → text conversion is necessary for the AI Agent.

✏️ 6. Edit Fields

The Edit Fields node creates a single clean user message called User Request.

It checks:

If text exists → use the text message

If no text → use the transcribed audio

This gives the AI Agent one clean input every time, no matter how the user communicates.

📄 7. Get Rows (Car Inventory)

This node reads all your car information from Google Sheets, such as:

🚗 Car Name

🏷 Model

📅 Year

💵 Price

🔗 Photo URL

✔ Availability

This becomes the data source for the AI Agent to find car matches.

📦 8. Aggregate Data

This node combines all the car rows into one structured dataset.

This makes it easier for the AI Agent to:

Search

Filter

Compare

Find matching cars

🤖 9. AI Agent
The AI Agent is the brain of the entire system.

It:

Reads the User Request

Understands what the customer wants

Searches the car inventory

Provides car details

Sends photo URLs

Books test drives

Saves leads

Responds politely and professionally

The AI Agent uses multiple tools to work correctly:

💬 10. Chat Model (Google Gemini)

This is the main language model that:

Understands user messages

Generates replies

Handles natural conversation

Provides correct information based on inventory

🧠 11. Memory

The Memory node helps the AI Agent remember:

Previous messages

Car the customer asked about

Whether the user wants a test drive

Follow-up context

Without memory, the AI forgets the conversation.

📅 12. Check Calendar (Get All Events)

This node checks available time slots in Google Calendar for test drives.

It ensures:

No double bookings

Correct date/time suggestions

Smooth scheduling

📝 13. Create Event (Book Test Drive)

When the customer confirms a time:

✔ The workflow automatically creates a test-drive event in Google Calendar.
✔ Event contains:

Customer name

Car model

Date & time

Notes

This makes booking fully automated.

📊 14. Append Row (Save Customer Lead)

This node saves:

Customer message

Car interest

Test-drive confirmation

Time & date

Contact details

Into Google Sheets, creating a complete customer lead database.

💬 15. Send Message

Finally, the workflow sends a professional WhatsApp message back to the customer with:

Car details

Price

Photo URL

Availability

Booking confirmation

Additional help

Everything is sent automatically.
