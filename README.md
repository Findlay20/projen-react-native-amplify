# Projen React Native Amplify

A [Projen](https://projen.io/) project template for creating React Native applications with AWS Amplify backend integration. This template provides a complete setup for building cross-platform mobile apps with authentication, data management, and cloud infrastructure.

## Features

- 🚀 **React Native with Expo** - Cross-platform mobile development
- 🔐 **AWS Amplify Authentication** - Built-in user authentication with UI components
- 📊 **AWS Amplify Data** - GraphQL API with real-time capabilities
- 🏗️ **Projen Configuration** - Infrastructure as Code for project management
- 📱 **Multi-platform Support** - iOS, Android, and Web
- 🔧 **TypeScript** - Full TypeScript support with proper configurations
- 🧪 **Testing Setup** - Jest testing framework with coverage reports
- 📦 **GitHub Packages** - Automated publishing to GitHub Packages
- 🔄 **CI/CD** - GitHub Actions workflows for build, test, and release

## Prerequisites

- Node.js (v18 or later)
- npm or yarn
- AWS CLI configured with appropriate permissions
- Expo CLI (`npm install -g @expo/cli`)
- For iOS development: Xcode
- For Android development: Android Studio

## Installation

### Using this template

```bash
npm install -g projen
mkdir my-react-native-app
cd my-react-native-app
npx projen new --from @findlay20/projen-react-native-amplify
```

### Manual installation

```bash
npm install @findlay20/projen-react-native-amplify
```

## Usage

### Creating a new project

```typescript
// .projenrc.ts
import { ReactNativeAmplifyProject } from '@findlay20/projen-react-native-amplify';

const project = new ReactNativeAmplifyProject({
  name: 'my-awesome-app',
  defaultReleaseBranch: 'main',
  author: 'Your Name',
  authorAddress: 'your.email@example.com',
  // Optional: specify React Native version
  reactNativeVersion: '0.79.2',
  reactVersion: '19.0.0',
});

project.synth();
```

### Development workflow

1. **Initialize the project**:
   ```bash
   npx projen
   ```

2. **Start the Amplify sandbox** (for backend development):
   ```bash
   npm run sandbox
   ```

3. **Start the Expo development server**:
   ```bash
   npm start
   ```

4. **Run on specific platforms**:
   ```bash
   npm run android    # Build and run on Android
   npm run ios        # Build and run on iOS
   npm run web        # Run on web browser
   npm run android:go # Start with Android simulator
   npm run ios:go     # Start with iOS simulator
   ```

### Available Scripts

- `npm start` - Start Expo development server
- `npm run sandbox` - Start Amplify sandbox environment
- `npm run prebuild` - Generate native code
- `npm run android` - Run on Android device/emulator
- `npm run ios` - Run on iOS device/simulator
- `npm run web` - Run in web browser
- `npm test` - Run tests with Jest
- `npm run build` - Build the project
- `npm run lint` - Run ESLint

## Project Structure

The generated project includes:

```
my-app/
├── amplify/                 # AWS Amplify backend configuration
│   ├── auth/               # Authentication resources
│   ├── data/               # Data/API resources
│   └── backend.ts          # Backend definition
├── assets/                 # App assets (icons, splash screens)
├── src/                    # React Native source code
│   └── HelloWorld.tsx      # Sample component
├── App.tsx                 # Main app component with Amplify setup
├── app.json               # Expo configuration
├── index.ts               # App entry point
└── .projenrc.ts           # Projen configuration
```

## AWS Amplify Integration

### Authentication

The template includes pre-configured AWS Cognito authentication:

```typescript
import { Authenticator } from '@aws-amplify/ui-react-native';

const App = () => {
  return (
    <Authenticator.Provider>
      <Authenticator>
        {/* Your app content */}
      </Authenticator>
    </Authenticator.Provider>
  );
};
```

### Data/API

GraphQL API with real-time capabilities is set up in `amplify/data/resource.ts`.

### Backend Deployment

Deploy your backend to AWS:

```bash
npx ampx sandbox --profile your-aws-profile
```

## Configuration Options

The `ReactNativeAmplifyProject` accepts these options:

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `reactVersion` | string | `'19.0.0'` | React version to use |
| `reactNativeVersion` | string | `'0.79.2'` | React Native version to use |
| `prMention` | string | - | GitHub username to mention in PRs |

## Dependencies

### Core Dependencies
- React Native with Expo
- AWS Amplify (React Native, UI components)
- TypeScript
- React Navigation ready

### Development Dependencies
- Projen for project management
- Jest for testing
- ESLint for code quality
- AWS CDK for infrastructure

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Run tests: `npm test`
5. Commit your changes: `git commit -m 'Add amazing feature'`
6. Push to the branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

## License

This project is licensed under the Apache-2.0 License - see the [LICENSE](LICENSE) file for details.

## Support

- 📖 [AWS Amplify Documentation](https://docs.amplify.aws/)
- 📱 [React Native Documentation](https://reactnative.dev/)
- 🏗️ [Projen Documentation](https://projen.io/)
- 🚀 [Expo Documentation](https://docs.expo.dev/)

## Author

**Cameron Findlay**
- Email: cammy.findlay20@gmail.com
- GitHub: [@Findlay20](https://github.com/Findlay20)

---