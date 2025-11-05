# React GraphQL Apollo Fullstack Tutorial 🚀

A complete, production-ready fullstack application demonstrating **React**, **GraphQL**, and **Apollo Client/Server** integration. This project showcases a space exploration app (similar to SpaceX missions) with authentication, booking, and real-time data fetching.

## 📋 Overview

**React GraphQL Apollo** is a comprehensive tutorial project that demonstrates:
- Modern fullstack development with React and GraphQL
- Apollo Client for frontend data management
- Apollo Server for GraphQL API
- User authentication and authorization
- Real-time data fetching and caching
- Best practices for GraphQL implementation

## ✨ Features

### Frontend (React + Apollo Client)
- 🚀 **Launch Dashboard** - Browse space missions and launches
- 🔐 **User Authentication** - JWT-based login system
- 🛒 **Trip Booking** - Book launches and manage cart
- 👤 **User Profile** - View booking history
- ⚡ **Optimistic Updates** - Instant UI feedback
- 🔄 **Cache Management** - Efficient data caching with Apollo

### Backend (Node.js + Apollo Server)
- 📡 **GraphQL API** - Type-safe API with schema validation
- 🔍 **Resolvers** - Query and mutation resolvers
- 💾 **SQLite Database** - Lightweight data persistence
- 🧪 **Comprehensive Tests** - E2E and integration tests
- 📊 **Data Sources** - Launch and User data sources

## 🛠️ Technology Stack

### Frontend
- **React** - UI library
- **Apollo Client** - GraphQL client
- **React Router** - Navigation
- **Styled Components** - CSS-in-JS styling

### Backend
- **Node.js** - Runtime environment
- **Apollo Server** - GraphQL server
- **SQLite** - Database
- **JWT** - Authentication

## 🚀 Getting Started

### Prerequisites

- Node.js 14+ and npm/yarn
- Git

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/bhanuchaddha/React-GraphQL-Apollo.git
cd React-GraphQL-Apollo
```

2. **Install server dependencies:**
```bash
cd server
npm install
```

3. **Install client dependencies:**
```bash
cd ../client
npm install
```

### Running the Application

1. **Start the GraphQL server:**
```bash
cd server
npm start
```

Server runs on `http://localhost:4000`

2. **Start the React client:**
```bash
cd client
npm start
```

Client runs on `http://localhost:3000`

## 📡 GraphQL API

### Queries

```graphql
# Get all launches
query GetLaunches {
  launches {
    id
    mission {
      name
    }
    rocket {
      name
    }
  }
}

# Get launch details
query GetLaunch($id: ID!) {
  launch(id: $id) {
    id
    mission {
      name
      missionPatch
    }
    rocket {
      name
      type
    }
  }
}
```

### Mutations

```graphql
# Login
mutation Login($email: String!) {
  login(email: $email) {
    token
  }
}

# Book trips
mutation BookTrips($launchIds: [ID]!) {
  bookTrips(launchIds: $launchIds) {
    success
    message
    launches {
      id
    }
  }
}
```

## 🏗️ Project Structure

```
React-GraphQL-Apollo/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── containers/     # Apollo-connected components
│   │   ├── pages/          # Page components
│   │   └── styles.js       # Styled components
│   └── package.json
├── server/                 # Apollo Server backend
│   ├── src/
│   │   ├── datasources/    # Data sources
│   │   ├── resolvers/      # GraphQL resolvers
│   │   ├── schema.js       # GraphQL schema
│   │   └── index.js        # Server entry point
│   └── package.json
└── README.md
```

## 🧪 Testing

### Backend Tests

```bash
cd server
npm test
```

Tests include:
- Integration tests
- E2E tests
- Resolver tests
- Data source tests

## 📚 Key Concepts Demonstrated

- **GraphQL Schema Design** - Type definitions and relationships
- **Apollo Client Hooks** - useQuery, useMutation, useLazyQuery
- **Cache Management** - Apollo cache updates and normalization
- **Optimistic UI** - Instant feedback for mutations
- **Error Handling** - GraphQL error handling patterns
- **Authentication** - JWT token management
- **Testing** - GraphQL API testing strategies

## 🔧 Configuration

### Apollo Client Config

```javascript
const client = new ApolloClient({
  uri: 'http://localhost:4000',
  cache: new InMemoryCache(),
  headers: {
    authorization: localStorage.getItem('token') || ''
  }
});
```

### Apollo Server Config

```javascript
const server = new ApolloServer({
  typeDefs,
  resolvers,
  dataSources: () => ({
    launchAPI: new LaunchAPI(),
    userAPI: new UserAPI()
  })
});
```

## 🎓 Learning Path

1. **Start with Server** - Understand GraphQL schema and resolvers
2. **Explore Client** - Learn Apollo Client hooks and caching
3. **Add Features** - Implement new queries and mutations
4. **Optimize** - Implement caching strategies and optimizations

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available for educational purposes.

## 🔗 Resources

- [Apollo GraphQL Documentation](https://www.apollographql.com/docs/)
- [GraphQL Documentation](https://graphql.org/learn/)
- [React Documentation](https://react.dev/)
- [Apollo Client Tutorial](https://www.apollographql.com/docs/react/)

## 🌟 Use Cases

- **Learning GraphQL** - Perfect tutorial project
- **Fullstack Development** - Modern stack reference
- **Apollo Integration** - Real-world Apollo patterns
- **Space App** - Building space-related applications
- **Booking Systems** - E-commerce patterns

---

**Built with React, GraphQL & Apollo ❤️**

