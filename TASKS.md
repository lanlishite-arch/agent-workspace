# Revenue Sprint Status

## Target

Settle at least 50 USDT to the designated Ethereum address within 24 hours from legitimate paid work.

## Active candidate

**SecureBananaLabs/bug-bounty — admin route RBAC bug**

- Candidate reward: $60 (per upstream bounty issue pattern).
- Verified against current `main`: `apps/api/src/routes/adminRoutes.js` applies authentication but no admin-role check.
- Verified token payload contains `role`, so role-based authorization can be enforced in middleware.
- Parent bounty process: issue #743 requires each solver to create their own issue and successful PR merge before payment.
- Proposed fix prepared and unit-tested locally: generic `requireRole(...roles)` middleware + admin route enforcement + tests.

## Current blocker

The connected GitHub App can write to repositories installed under the user's account, but cannot create issues directly in the upstream third-party repository. To submit, the user must create the upstream issue and fork the repository once; after the fork is granted to the connector, the agent can commit and open the PR.
