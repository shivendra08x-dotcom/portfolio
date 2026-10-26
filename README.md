# Shivendra Sharma — Personal Profile

A responsive personal portfolio website for introducing Shivendra Sharma, showcasing skills and projects, and providing interactive weather and AI chat features.

## Features

- **About and skills:** A short profile and a list of technical skills.
- **Project gallery:** Five projects with repository links and technology tags.
- **Project search:** Filter projects by title, description, or technology.
- **Weather lookup:** Retrieve a city's current temperature and conditions using the OpenWeatherMap API.
- **AI portfolio assistant:** Ask questions about the profile, skills, and projects. Simple greetings receive an immediate response; other questions use the chat API.
- **Light and dark themes:** Switch themes with the floating button.
- **Responsive layout:** Adapts to smaller screens.

## Project files

| File | Purpose |
| --- | --- |
| `index.html` | Portfolio page structure and content |
| `style.css` | Main layout, colors, responsive styles, and theme toggle |
| `script.js` | Theme toggle, project search, and weather lookup |
| `chatbot.css` | AI chat widget styles |
| `chatbot.js` | Browser-side chat behavior and requests to `/api/chat` |
| `chat.js` | Serverless chat handler that calls the Groq API |

The profile image path in the page is a placeholder (`images/PLACEHOLDER-profile.jpg`). Add a profile photo at that path or update the image path in `index.html`.

## Run locally

For the portfolio, project search, theme toggle, and weather feature, open `index.html` in a browser. An internet connection is needed for Google Fonts and weather requests.

For the AI assistant, serve the project with a platform that supports the `/api/chat` serverless route. The provided `chat.js` is written in the Vercel-style request/response format and should be deployed as `api/chat.js` so it is available at `/api/chat`. A static file preview alone will not provide this endpoint.

Configure the server environment variable `GROQ_API_KEY` with a valid Groq API key before using the AI chat. Keep this key on the server; do not put it in browser JavaScript or commit it to the repository. The chat handler uses the `openai/gpt-oss-20b` model through Groq's OpenAI-compatible API.

## API configuration

- **Weather:** `script.js` calls OpenWeatherMap's current weather endpoint and expects an API key. Replace the existing key in the script with your own valid key before publishing. Since browser-side keys are visible to visitors, restrict the key through your provider's settings where possible or move weather requests behind a server endpoint.
- **AI chat:** Set `GROQ_API_KEY` in the deployment environment. The browser sends the question, portfolio text, and up to one recent exchange to `/api/chat`.

## Customization

Edit the text, skills, project details, and contact links in `index.html`. Adjust colors, spacing, and responsive behavior in `style.css` and `chatbot.css`. Update the interaction logic in `script.js` or `chatbot.js` as needed.

## Technologies

HTML · CSS · JavaScript · OpenWeatherMap API · Groq API
