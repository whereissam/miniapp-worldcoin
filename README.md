# Next.js MiniKit Template

This template provides a minimal setup to get Next.js working with MiniKit for World ID integration.

## Prerequisites

- [Node.js](https://nodejs.org/) (v16 or higher)
- [pnpm](https://pnpm.io/) package manager
- [ngrok](https://ngrok.com/) for local development tunneling

## Setup

1. Clone the repository and install dependencies:

```bash
cp .env.example .env
pnpm i
```

2. Configure environment variables:

- Open `.env` and update the following variables:
  - `NEXTAUTH_URL`: Your application URL (use ngrok URL in development)
  - `NEXT_PUBLIC_WLD_APP_ID`: Your World ID App ID from the Developer Portal
  - `NEXT_PUBLIC_WLD_ACTION`: Your World ID Action Name
  - `NEXT_PUBLIC_WLD_API_BASE_URL`: World ID API Base URL
  - `NEXTAUTH_SECRET`: Your NextAuth secret (generate one if needed)

3. Set up ngrok for local development:

```bash
ngrok http 3000
```

4. Update redirect URIs:
- Go to the [World ID Developer Portal](https://developer.worldcoin.org/)
- Navigate to your app settings
- Add the following redirect URI: `{YOUR_NGROK_URL}/api/auth/callback/worldcoin`
  (e.g., `https://your-ngrok-subdomain.ngrok.io/api/auth/callback/worldcoin`)

5. Start the development server:

```bash
pnpm dev
```

## Development

- Open [http://localhost:3000](http://localhost:3000) to view your app locally
- Use your ngrok URL to test the app as a mini app

## Documentation

- [MiniKit Documentation](https://minikit-docs.vercel.app/mini-apps)
- [World ID Developer Portal](https://developer.worldcoin.org/)

## Troubleshooting

### Common Issues

1. **Invalid redirect_uri error**:
   - Ensure your redirect URI in the Developer Portal exactly matches your callback URL
   - The redirect URI should include `/api/auth/callback/worldcoin`
   - Check that you're using the correct ngrok URL if testing locally

2. **Authentication Issues**:
   - Verify that `NEXTAUTH_URL` matches your current deployment URL
   - For local development, this should be your ngrok URL

## Contributing

Please read our contributing guidelines before submitting pull requests.

## License

[MIT License](LICENSE)
