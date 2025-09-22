# Ripple.js + Shogun Core Todo App

A modern, full-stack decentralized todo application built with Ripple.js and Shogun Core (GunDB). This application demonstrates real-time, peer-to-peer data synchronization with user authentication, showcasing how to build decentralized applications with modern web technologies.

## 🚀 Features

- **🎯 Ripple.js Framework**: Modern reactive UI framework with TypeScript support
- **🌐 Decentralized Storage**: Built on GunDB for peer-to-peer data synchronization
- **🔐 Authentication System**: Multiple auth methods via Shogun Core (username/password, WebAuthn, Web3, OAuth)
- **⚡ Real-time Sync**: Automatic data synchronization across all connected peers
- **📱 Modern UI**: Clean, responsive design with vanilla CSS
- **🛠️ TypeScript**: Full type safety and IntelliSense support
- **🔧 Vite**: Fast development server and optimized builds
- **📦 Complete Implementation**: Fully functional todo app with all features implemented

## 🏗️ Architecture

This application is a complete decentralized todo app featuring:

- **User Authentication**: Login/signup with username and password
- **Real-time Data**: Todos sync instantly across all connected devices
- **User Space**: Each user has their own private data space
- **Peer Network**: Connects to multiple GunDB relay servers for redundancy
- **Modern Hooks**: Custom Ripple.js hooks for GunDB operations

## 📋 Prerequisites

- Node.js 18+ 
- npm, yarn, or pnpm
- Modern web browser with ES2020+ support

## 🚀 Quick Start

1. **Clone and install dependencies:**

    ```bash
    git clone <repository-url>
    cd my-app
    npm install # or yarn install
    ```

2. **Start the development server:**

    ```bash
    npm run dev
    ```

3. **Open your browser:**

    Navigate to `http://localhost:5173` to see the application running.

4. **Build for production:**

    ```bash
    npm run build
    ```

## 🎯 What's Included

### Core Components

- **`App.ripple`**: Main application component with authentication and todo management
- **`useGunInstance.ripple`**: Hook for initializing GunDB connection
- **`useGunAuth.ripple`**: Hook for user authentication operations
- **`useGunData.ripple`**: Hook for data collection management

### Todo App Features

1. **Authentication Flow**
   - User registration with username, email, and password
   - Secure login with session management
   - Logout functionality

2. **Real-time Data Management**
   - Create, read, update, and delete todos
   - Automatic synchronization across peers
   - Optimistic UI updates

3. **User Space Operations**
   - Private user data storage
   - Collection-based data organization
   - Real-time updates

## 🔧 Configuration

### GunDB Peers

The application connects to multiple GunDB relay servers for redundancy:

```typescript
const peers = [
  'https://relay.shogun-eco.xyz/gun',
  'https://peer.wallie.io/gun',
  'https://v5g5jseqhgkp43lppgregcfbvi.srv.us/gun'
];
```

### Shogun Core Integration

The application uses Shogun Core's Simple API for easy GunDB operations:

```typescript
import { quickStart, Gun } from "shogun-core";

// Initialize Gun instance
const gun = Gun({ peers: ['https://relay.shogun-eco.xyz/gun'] });

// Quick start with simple API
const shogun = quickStart(gun, 'my-app');
await shogun.init();
```

## 📚 Available Scripts

- **`npm run dev`** - Start development server with hot reload
- **`npm run build`** - Build for production
- **`npm run preview`** - Preview production build locally
- **`npm run format`** - Format code with Prettier
- **`npm run format:check`** - Check code formatting

## 🎨 Code Formatting

This template includes Prettier with the Ripple plugin for consistent code formatting.

### Configuration

Prettier is configured in `.prettierrc` with the following settings:

- Uses tabs for indentation
- Single quotes for strings
- 100 character line width
- Includes the `prettier-plugin-ripple` for `.ripple` file formatting

### VS Code Integration

For the best development experience, install these extensions:

- [Prettier VS Code extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Ripple VS Code extension](https://marketplace.visualstudio.com/items?itemName=ripplejs.ripple-vscode-plugin)

## 🔌 Custom Hooks

### `useGunInstance`

Initializes and manages GunDB connection:

```typescript
const shogun = useGunInstance({
  peers: ['https://relay.shogun-eco.xyz/gun']
});
```

### `useGunAuth`

Handles user authentication:

```typescript
const { user, isLoggedIn, login, signup, logout } = useGunAuth(shogun);
```

### `useGunCollection`

Manages data collections with real-time sync:

```typescript
const { items, loading, error, add, update, remove } = useGunCollection(
  shogun, 
  'todos', 
  []
);
```

## 🌐 Decentralized Features

### Peer-to-Peer Data Sync

- **Automatic Synchronization**: Data changes sync instantly across all connected peers
- **Offline Support**: Works offline and syncs when connection is restored
- **Conflict Resolution**: GunDB handles data conflicts automatically
- **Redundancy**: Multiple relay servers ensure data availability

### User Privacy

- **End-to-End Encryption**: User data is encrypted using GunDB's SEA (Security, Encryption, Authorization)
- **Private User Space**: Each user has their own encrypted data space
- **No Central Server**: No single point of failure or data control

## 🛠️ Development

### Project Structure

```
src/
├── App.ripple              # Main application component
├── hooks/
│   ├── useGunInstance.ripple    # GunDB connection hook
│   ├── useGunAuth.ripple        # Authentication hook
│   └── useGunData.ripple        # Data management hook
└── main.ts                 # Application entry point
```

### Extending the Todo App

1. **Add new todo features** like categories, due dates, or priorities
2. **Create additional components** as `.ripple` files
3. **Use Shogun Core API** for more complex data operations
4. **Leverage Ripple.js reactivity** for real-time UI updates

### TypeScript Support

The project includes full TypeScript support with:

- Type definitions for all Shogun Core APIs
- Ripple.js component typing
- GunDB type safety
- Custom hook type definitions

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

The build output will be in the `dist/` directory, ready for deployment to any static hosting service.

### Deployment Options

- **Vercel**: Connect your repository for automatic deployments
- **Netlify**: Deploy from Git with continuous integration
- **GitHub Pages**: Host directly from your repository
- **Any Static Host**: Upload the `dist/` folder to any web server

## 📖 Learn More

### Documentation

- [Ripple.js Documentation](https://github.com/trueadm/ripple)
- [Shogun Core Documentation](https://shogun-core-docs.vercel.app/)
- [GunDB Documentation](https://gun.eco/docs/)
- [Vite Documentation](https://vitejs.dev/)

### Community

- [Shogun Ecosystem Telegram](https://t.me/shogun_eco)
- [GunDB Community](https://gitter.im/amark/gun)
- [Ripple.js GitHub](https://github.com/trueadm/ripple)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Ripple.js](https://github.com/trueadm/ripple) - Modern reactive UI framework
- [Shogun Core](https://github.com/scobru/shogun-core) - Decentralized authentication and data management
- [GunDB](https://gun.eco/) - Peer-to-peer database
- [Vite](https://vitejs.dev/) - Fast build tool and dev server
