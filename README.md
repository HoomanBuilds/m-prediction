# Moros Prediction

Private prediction-market implementation for Stellar and Soroban, with Circle USDC collateral, encrypted orders, aggregate LMSR execution, isolated liquidity, and proof-bound settlement.

This repository contains the application, contracts, Circom circuits, committee implementation, market services, deployment records, tests, recovery tools, and technical whitepaper. Public hosting and background services are currently stopped. Repository preparation does not restart services or deploy contracts.

## Architecture

- `web/`: Next.js market application, wallet integration, portfolio, liquidity, encrypted recovery, and recovery scripts.
- `contracts/`: Market factory, LMSR markets, isolated and pooled liquidity, shielded collateral, verifiers, resolvers, and privacy types.
- `circuits/private/`: Private order, settlement, liquidity, treasury, and batch circuit tooling.
- `services/committee/`: Committee cryptography, coordination, and persistence.
- `services/`: Private relay, indexing, market registration, batching, resolution, and operations.
- `deployments/`: Existing public mainnet and testnet deployment records.

## Existing mainnet contracts

| Component | Address |
| --- | --- |
| `verifier` | `CD4RRUKDBQ6IP6LQJYTBGF5OOVFHIJWUULJCV52LANOLQEGYG4C5JQWL` |
| `resolver` | `CAUDDAZVWDGWHDC6IHV66RAQ2CTLMXGXUEOT6VNU7OF4ACZPMXUEDLWA` |
| `resolverRegistry` | `CCK6GQ7DQDWCBZEIGVGDZ3AF3STHHXNVFYDKMFU634YHA7QDIQY3YKEB` |
| `sharedVault` | `CBXZUAUEFAXZFRL4J7DTLS3GLAEY5OMIBBAUI672KJJE7FGU5LQJGXXL` |
| `liquidityPool` | `CB45XJ65Y46J2KGLUI6ZGUQ6C5EN7KS2BGI636ISIKSSBHVDYICPWP3F` |
| `factory` | `CDJ44IRLMZFEA4XY3J2XJMFLD4XIB3OIMRTYWBQZVX5ESBXMHNTOO3O7` |

The public proving manifest is `deployments/private-mainnet-proving.json`. Private configuration, deployment state, Stellar identity files, and committee secrets remain outside Git.

## Local validation

```bash
npm --prefix services ci
npm --prefix services test
npm --prefix web ci
npm --prefix web run test:unit
npm --prefix web run build
```

The explicit deployment and on-chain test tools are separate from these local checks. Read `services/README.md` and `services/OPS.md` before operating a deployment.

## Whitepaper and working documentation

- [PDF](docs/Moros-Technical-Whitepaper.pdf)
- [DOCX](docs/Moros-Technical-Whitepaper.docx)

The complete local planning, specification, demo, and source material is preserved under ignored documentation and reference folders. Public proof artifacts remain in their ignored build directories.
