### Accounts RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ✅        | ✅          | ✅          | ✅    | ✅    | ✅    |
| Suspend | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Delete  | ✅        | ✅          | ✅          | ❌        | ✅    | ✅    |


### Accounts ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ✅        | ✅          | ✅          | Only own    | Only own    | ✅    |
| Suspend | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Delete  | ✅        | ✅          | ✅          | ❌        | Only own    | ✅    |

### Investments RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ❌        | ✅          | ✅          | ❌    | ❌    | ✅    |
| Approve | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| View | ❌        | ❌          | ❌          | ✅        | ✅    | ✅    |

### Investments ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌        | ❌    | 2FA (Optional)    |
| Update  | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌    | ❌    | 2FA (Optional)    |
| Approve | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌        | ❌    | 2FA (Optional)    |
| View | ❌        | ❌          | ❌          | Own        | Own    | 2FA    |

