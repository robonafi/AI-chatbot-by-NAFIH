<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Chatbot BY NAFIH</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom styles for Inter font and overall layout */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        .chat-container {
            width: 100%;
            max-width: 500px;
            height: 80vh; /* Set a fixed height for the chat window */
            display: flex;
            flex-direction: column;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }
        .chat-messages {
            flex-grow: 1;
            padding: 20px;
            overflow-y: auto;
            background-color: #e2e8f0; /* Light background for messages */
            border-bottom: 1px solid #cbd5e1;
        }
        .message-bubble {
            max-width: 80%;
            padding: 10px 15px;
            border-radius: 20px;
            margin-bottom: 10px;
            word-wrap: break-word;
        }
        .user-message {
            background-color: #3b82f6; /* Blue for user messages */
            color: white;
            align-self: flex-end;
            margin-left: auto;
            border-bottom-right-radius: 4px;
        }
        .bot-message {
            background-color: #f8fafc; /* Light gray for bot messages */
            color: #333;
            align-self: flex-start;
            margin-right: auto;
            border-bottom-left-radius: 4px;
        }
        .loading-indicator {
            display: flex;
            justify-content: center;
            padding: 10px;
            color: #64748b;
            font-style: italic;
        }
        .chat-input-area {
            display: flex;
            flex-direction: column; /* Stack input and buttons vertically */
            padding: 15px;
            border-top: 1px solid #cbd5e1;
            background-color: #ffffff;
        }
        .input-and-send {
            display: flex;
            width: 100%;
            margin-bottom: 10px; /* Space between input and feature buttons */
        }
        .chat-input {
            flex-grow: 1;
            padding: 10px 15px;
            border: 1px solid #cbd5e1;
            border-radius: 25px;
            outline: none;
            font-size: 16px;
            margin-right: 10px;
        }
        .send-button {
            background-color: #2563eb;
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            border: none;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }
        .send-button:hover {
            background-color: #1d4ed8;
        }
        .send-button:disabled {
            background-color: #93c5fd;
            cursor: not-allowed;
        }
        .feature-buttons {
            display: flex;
            gap: 10px; /* Space between feature buttons */
            justify-content: center;
            width: 100%;
        }
        .feature-button {
            background-color: #10b981; /* Green for feature buttons */
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            border: none;
            cursor: pointer;
            font-size: 14px;
            transition: background-color 0.3s ease;
            flex-grow: 1; /* Allow buttons to grow and fill space */
            max-width: 200px; /* Limit max width for larger screens */
        }
        .feature-button:hover {
            background-color: #059669;
        }
        .feature-button:disabled {
            background-color: #a7f3d0;
            cursor: not-allowed;
        }

        /* Responsive adjustments */
        @media (max-width: 600px) {
            .chat-container {
                height: 90vh;
                border-radius: 0;
            }
            .feature-buttons {
                flex-direction: column; /* Stack feature buttons vertically on small screens */
                align-items: center;
            }
            .feature-button {
                width: 100%;
                max-width: none; /* Remove max-width on small screens */
            }
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-messages" id="chat-messages">
            <div class="message-bubble bot-message">
                Hello! How can I assist you today?
            </div>
        </div>
        <div class="chat-input-area">
            <div class="input-and-send">
                <input type="text" id="user-input" class="chat-input" placeholder="Type your message...">
                <button id="send-button" class="send-button">Send</button>
            </div>
            <div class="feature-buttons">
                <button id="summarize-button" class="feature-button">✨ Summarize Last Bot Message</button>
                <button id="creative-idea-button" class="feature-button">✨ Get Creative Idea</button>
            </div>
        </div>
    </div>

    <script>
        const chatMessages = document.getElementById('chat-messages');
        const userInput = document.getElementById('user-input');
        const sendButton = document.getElementById('send-button');
        const summarizeButton = document.getElementById('summarize-button');
        const creativeIdeaButton = document.getElementById('creative-idea-button');

        // Function to add a message to the chat display
        function addMessage(text, sender) {
            const messageDiv = document.createElement('div');
            messageDiv.classList.add('message-bubble');
            messageDiv.classList.add(sender === 'user' ? 'user-message' : 'bot-message');
            messageDiv.textContent = text;
            chatMessages.appendChild(messageDiv);
            // Scroll to the bottom of the chat
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        // Function to show a loading indicator
        function showLoadingIndicator(text = 'Bot is typing...') {
            const loadingDiv = document.createElement('div');
            loadingDiv.id = 'loading-indicator';
            loadingDiv.classList.add('loading-indicator');
            loadingDiv.textContent = text;
            chatMessages.appendChild(loadingDiv);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        // Function to remove the loading indicator
        function removeLoadingIndicator() {
            const loadingDiv = document.getElementById('loading-indicator');
            if (loadingDiv) {
                loadingDiv.remove();
            }
        }

        // Function to disable/enable all interactive elements during API call
        function setInteractiveElementsDisabled(disabled) {
            sendButton.disabled = disabled;
            userInput.disabled = disabled;
            summarizeButton.disabled = disabled;
            creativeIdeaButton.disabled = disabled;
        }

        // Function to send message to Gemini API for general chat
        async function sendMessageToBot() {
            const message = userInput.value.trim();
            if (message === '') return;

            addMessage(message, 'user');
            userInput.value = ''; // Clear input field
            setInteractiveElementsDisabled(true); // Disable all elements
            showLoadingIndicator(); // Show loading indicator

            try {
                // Initialize chat history with the current user message
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: message }] });

                const payload = { contents: chatHistory };
                const apiKey = ""; // API key is intentionally left empty; Canvas runtime will provide it.
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const result = await response.json();

                removeLoadingIndicator(); // Remove loading indicator

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const botResponse = result.candidates[0].content.parts[0].text;
                    addMessage(botResponse, 'bot');
                } else {
                    addMessage("Sorry, I couldn't get a response. Please try again.", 'bot');
                    console.error("Unexpected API response structure:", result);
                }

            } catch (error) {
                removeLoadingIndicator(); // Remove loading indicator even on error
                addMessage("An error occurred. Please try again later.", 'bot');
                console.error("Error calling Gemini API:", error);
            } finally {
                setInteractiveElementsDisabled(false); // Re-enable all elements
                userInput.focus(); // Focus input for next message
            }
        }

        // Function to summarize the last bot message
        async function summarizeLastBotMessage() {
            // Find the last bot message in the chat display
            const botMessages = chatMessages.querySelectorAll('.bot-message');
            if (botMessages.length === 0) {
                addMessage("There's no bot message to summarize yet. Please chat with me first!", 'bot');
                return;
            }

            const lastBotMessage = botMessages[botMessages.length - 1].textContent;
            const prompt = `Please summarize the following text concisely: "${lastBotMessage}"`;

            setInteractiveElementsDisabled(true);
            showLoadingIndicator('Summarizing...');

            try {
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: prompt }] });

                const payload = { contents: chatHistory };
                const apiKey = "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const result = await response.json();

                removeLoadingIndicator();

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    const summary = result.candidates[0].content.parts[0].text;
                    addMessage(`Summary: ${summary}`, 'bot');
                } else {
                    addMessage("Sorry, I couldn't summarize the message. Please try again.", 'bot');
                    console.error("Unexpected API response structure for summarization:", result);
                }

            } catch (error) {
                removeLoadingIndicator();
                addMessage("An error occurred during summarization. Please try again later.", 'bot');
                console.error("Error calling Gemini API for summarization:", error);
            } finally {
                setInteractiveElementsDisabled(false);
                userInput.focus();
            }
        }

        // Function to get a creative idea
        async function getCreativeIdea() {
            const prompt = "Give me a creative and unique idea for a fun activity or project.";

            setInteractiveElementsDisabled(true);
            showLoadingIndicator('Generating creative idea...');

            try {
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: prompt }] });

                const payload = { contents: chatHistory };
                const apiKey = "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                const result = await response.json();

                removeLoadingIndicator();

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts && // Corrected this line
                    result.candidates[0].content.parts.length > 0) { // Corrected this line
                    const idea = result.candidates[0].content.parts[0].text;
                    addMessage(`Creative Idea: ${idea}`, 'bot');
                } else {
                    addMessage("Sorry, I couldn't generate a creative idea. Please try again.", 'bot');
                    console.error("Unexpected API response structure for creative idea:", result);
                }

            } catch (error) {
                removeLoadingIndicator();
                addMessage("An error occurred while generating a creative idea. Please try again later.", 'bot');
                console.error("Error calling Gemini API for creative idea:", error);
            } finally {
                setInteractiveElementsDisabled(false);
                userInput.focus();
            }
        }

        // Event listeners
        sendButton.addEventListener('click', sendMessageToBot);
        userInput.addEventListener('keypress', function(event) {
            if (event.key === 'Enter') {
                sendMessageToBot();
            }
        });
        summarizeButton.addEventListener('click', summarizeLastBotMessage);
        creativeIdeaButton.addEventListener('click', getCreativeIdea);
    </script>
</body>
</html>
