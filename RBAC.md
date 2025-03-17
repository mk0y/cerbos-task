### Accounts RBAC

| Resource Type | Action  | IT Admin | Jr Manager | Sr Manager | User      | CFO  |
|--------------|---------|----------|------------|------------|-----------|------|
| **Account**  | Create  | ✅        | ✅          | ✅          | ❌        | ✅    |
|              | Update  | ✅        | ✅          | ✅          | ✅ (own)  | ✅    |
|              | Suspend | ✅        | ❌          | ✅          | ❌        | ✅    |
|              | Delete  | ✅        | ❌          | ✅          | ❌        | ✅    |

# RBAC Matrix for Investments

| Resource Type  | Action  | IT Admin | Jr Manager | Sr Manager | User (Regular) | CFO  |
|---------------|---------|----------|------------|------------|---------------|------|
| **Investment** | Create  | ❌        | ✅ (≤ $100K, Assigned Regions) | ✅ (≤ $1M, Assigned Regions) | ❌             | ✅    |
|               | Update  | ❌        | ✅ (≤ $100K, Assigned Regions) | ✅ (≤ $1M, Assigned Regions) | ❌             | ✅    |
|               | View    | ❌        | ✅ (Only Assigned Region) | ✅ (Only Assigned Region) | ✅ (Own Only)  | ✅    |
|               | Approve | ❌        | ✅ (Only Assigned Region, Requires 2FA) | ✅ (Only Assigned Region, Requires 2FA) | ❌             | ✅    |
