# CoffeeBreak Development Stack

A complete Docker Compose development environment for the CoffeeBreak platform. This repository contains all the necessary configuration and services to run CoffeeBreak locally for development purposes.

## Setup

1. **Clone the repository with submodules:**
   ```bash
   git clone --recurse-submodules https://github.com/PI-coffeeBreak/coffeebreak-devstack.git
   cd coffeebreak-devstack
   ```

2. **Copy environment file:**
   ```bash
   cp .env.example .env
   ```

3. **Start the services:**
   ```bash
   docker compose up
   ```

4. **Configure Keycloak client secret:**
   - Access Keycloak admin console at http://localhost/auth
   - Login with admin credentials (default: username `admin`, password `admin` - or check your .env file if changed)
   - Navigate to: Realms → coffeebreak → Clients → fastapi-client → Credentials
   - Copy the "Client Secret" value
   - Add it to your `.env` file:
     ```bash
     KEYCLOAK_CLIENT_SECRET=your-copied-secret-here
     ```

5. **Restart the services:**
   ```bash
   docker compose restart
   ```

## Access Applications

- **Admin Interface**: http://localhost:3001
- **Event App**: http://localhost
- **API Documentation**: http://localhost/api/v1/docs

## Updating Submodules

The submodules are configured to track the `dev` branch. To update all submodules to the latest dev branch:

```bash
git submodule update --remote
```

## Contributing

1. Make changes in the appropriate submodule directory
2. Test your changes with the development stack
3. Commit changes in the submodule
4. Update this repository if configuration changes are needed

## Support

For issues related to:
- **Core API**: Open issues in [PI-coffeeBreak/core](https://github.com/PI-coffeeBreak/core)
- **Frontend**: Open issues in [PI-coffeeBreak/frontend](https://github.com/PI-coffeeBreak/frontend)
- **Event App**: Open issues in [PI-coffeeBreak/event-app](https://github.com/PI-coffeeBreak/event-app)
- **Development Stack**: Open issues in this repository