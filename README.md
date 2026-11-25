# QuantRWA

> Don't let your assets sit around: tokenize real-world assets and let agentic trading put them to work.

Built at **Hook 'Em Hacks 2026** by Collin Chen and Jai Narayan.

🏆 **Devpost:** https://devpost.com/software/quantrwa
🎥 **Demo video:** https://www.youtube.com/watch?v=AVDLeIvMF40
🌐 **Portfolio:** https://jaifnarayan.github.io/#projects
🔀 Forked from [CollinEChen/QuantRWA](https://github.com/CollinEChen/QuantRWA)

## What it does

Upload a photo of a high-value physical item, such as a watch, a piece of art or electronics, and QuantRWA does the rest:

1. **Gemini Vision** appraises the item and assigns a fraud-risk score.
2. Assets that pass the security threshold are minted as **Solana SPL tokens** and split into **10,000 tradable shares**.
3. An **AI trading layer** manages a portfolio of those RWA tokens alongside SOL and USDC.
4. Every action is written to a **MongoDB Atlas** audit trail.

## Architecture

| Layer | Details |
|---|---|
| AI | Gemini Vision for multimodal appraisal and deepfake checks, plus agentic trading logic |
| Security | AWS Lambda enclave backed by AWS Secrets Manager. It keeps the Solana vault key off the frontend, requires an HMAC signature for every mint, and rejects assets with a risk score above 30 |
| Blockchain | Solana SPL tokens and Metaplex Core |
| Frontend and data | Next.js, Tailwind CSS and Framer Motion on Vercel, with MongoDB Atlas for time-series tick data and audit logs |

**Built with:** TypeScript · Next.js · React · Node.js · Solana · AWS · Gemini API · MongoDB

## Running locally

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

## What's next

- Certified appraisers who co-sign the AWS signature for human verification
- A peer-to-peer secondary marketplace for RWA shares
- DeFi features, such as using tokenized assets as loan collateral
