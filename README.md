🦷 DentAI Care – AI-Powered Dental Analyzer

📖 Overview

DentAI Care is an AI-driven workflow built with n8n and Lovable that analyzes dental images and provides instant insights about teeth condition, professional advice, and recommended care.
It’s designed to make dental health evaluation simple, fast, and accessible through an automated workflow.

⚙️ Workflow Components

🧩 1. Webhook Trigger

Purpose: Receives the image sent from Lovable (Frontend).
Function: When a user uploads or sends a photo, the webhook captures it and starts the workflow automatically.
Response Setting: Configured to “Respond when last node finishes”, so the response is sent only after the AI analysis is complete — ensuring users receive the final, processed result.

🤖 2. AI Agent Node

Purpose: Handles the main image analysis.
Function: Sends the received image to the Google Gemini Chat Model for intelligent dental condition analysis

🧠 3. Google Gemini Chat Model

Purpose: Analyzes the dental image and generates a structured response.
Function: Provides three key outputs:
Teeth Condition Analysis
Professional Advice
Recommended Care

🧹 4. Structured Output Parser

Purpose: Cleans and organizes the AI’s raw output into a clear, structured format.
Function: Ensures the response is neat, readable, and ready to display on the Lovable frontend.
