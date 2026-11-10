# Prediction contracts

The workspace contains the market factory, LMSR market, market liquidity vault, pooled liquidity vault, shielded collateral vault, Groth16 verifier, privacy types, price resolver, event resolver, and resolver registry. The earlier isolated-pool prototype is preserved under `shielded-pool/` and remains outside the workspace.

```bash
cargo test --manifest-path contracts/Cargo.toml --workspace
```

Mainnet and testnet contract records live in `../deployments/`. Existing deployed addresses, identities, proof schemas, and cryptographic domains are preserved.
