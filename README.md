# Meme Generator

An AI-powered meme generator mobile app that runs **entirely on-device** using Meta's ExecuTorch runtime. Generate memes with AI-generated text and images - no cloud APIs, no internet required for inference.

## Features

- **On-Device AI Inference** - All AI models run locally on your device for privacy and offline capability
- **AI Text Generation** - Uses Llama 3.2 1B (SpinQuant) to generate witty meme captions based on your prompt
- **AI Image Generation** - Uses BK-SDM Tiny (Stable Diffusion) to create meme images directly on your phone
- **Chat Interface** - Simple conversational UI to describe your meme idea and get instant results
- **Cross-Platform** - Works on both iOS and Android

## How It Works

1. **Describe your meme** - Enter a prompt describing the meme you want to create
2. **AI generates text** - Llama 3.2 creates clever top and bottom text for your meme
3. **AI generates image** - Stable Diffusion creates a matching meme image
4. **View your meme** - The generated image is displayed with the AI-generated captions overlaid

## Tech Stack

- **React Native** with Expo
- **[react-native-executorch](https://github.com/software-mansion/react-native-executorch)** - On-device AI inference
- **Llama 3.2 1B SpinQuant** - Text generation model
- **BK-SDM Tiny vPred 512** - Stable Diffusion image generation model
- **TypeScript** for type safety

## Prerequisites

- Node.js 18+
- Yarn
- Xcode (for iOS development)
- Android Studio (for Android development)

## Installation

Install dependencies:

```bash
yarn
```

## Running the App

### iOS

```bash
yarn expo run:ios
```

### Android

```bash
yarn expo run:android
```

## First Launch

On first launch, the app will download the AI models (~500MB+). This is a one-time download - subsequent launches will use the cached models. A loading spinner shows the download progress for both the text and image models.

## Architecture

```
app/
├── index.tsx          # Main screen with chat UI and AI integration
├── _layout.tsx        # App navigation layout
components/
├── ImageMessages.tsx  # Chat message list for meme display
├── ImageMessageItem.tsx # Individual meme message component
├── Spinner.tsx        # Loading indicator with download progress
utils/
├── tools.ts           # Device tool integrations (brightness, calendar)
```

## License

MIT