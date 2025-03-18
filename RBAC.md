### 1.1 Accounts RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ✅        | ✅          | ✅          | ✅    | ✅    | ✅    |
| Suspend | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Delete  | ✅        | ✅          | ✅          | ❌        | ✅    | ✅    |


### 1.2 Accounts ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ✅        | ✅          | ✅          | Own    | Own    | ✅    |
| Suspend | ✅        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Delete  | ✅        | ✅          | ✅          | ❌        | Own    | ✅    |

### 2.1 Investments RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Update  | ❌        | ✅          | ✅          | ❌    | ❌    | ✅    |
| Approve | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| View | ❌        | ❌          | ❌          | ✅        | ✅    | ✅    |

### 2.2 Investments ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Create  | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌        | ❌    | 2FA (Optional)    |
| Update  | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌    | ❌    | 2FA (Optional)    |
| Approve | ❌        | <= 100k, Region, 2FA (Optional)          | <= 1M, Region, 2FA (Optional)          | ❌        | ❌    | 2FA (Optional)    |
| View | ❌        | ❌          | ❌          | Own        | Own    | 2FA    |

### 3.1 Reports RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Run  | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| View  | ❌        | ✅          | ✅          | ❌    | ❌    | ✅    |
| Edit | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |
| Share_ext | ❌        | ❌          | ✅          | ❌        | ❌    | ✅    |

### 3.2 Reports ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| Run  | ❌        | <= 100k, Region    | <= 1M, Region          | ❌        | ❌    | ✅    |
| View  | ❌        | <= 100k, Region    | <= 1M, Region          | ❌    | ❌    | ✅    |
| Edit | ❌        | <= 100k, Region    | <= 1M, Region          | ❌        | ❌    | ✅    |
| Share_ext | ❌        | ❌          | P.can_share, R.sharable          | ❌        | ❌    | R.sharable    |

### 4.1 Transactions RBAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| View  | ❌        | ✅          | ✅          | ✅        | ✅    | ✅    |
| Approve  | ❌        | ✅          | ✅          | ❌    | ❌    | ✅    |
| Cancel | ❌        | ✅          | ✅          | ❌        | ❌    | ✅    |

### 4.2 Transactions ABAC

| Action  | IT Admin | Jr Manager | Sr Manager | User      | Admin | CFO  |
|---------|----------|------------|------------|-----------|-------|------|
| View  | ❌        | <= 100k, Region <br> 2FA (required), within 10m          | <= 1M, Region <br> 2FA (required), within 10m          | Own        | Own    | 2FA (required), within 10m    |
| Approve  | ❌        | <= 100k, Region <br> 2FA (required), within 10m          | <= 1M, Region <br> 2FA (required), within 10m           | ❌    | ❌    | 2FA (required), within 10m    |
| Cancel | ❌        | <= 100k, Region <br> 2FA (required), within 10m          | <= 1M, Region <br> 2FA (required), within 10m          | ❌        | ❌    | 2FA (required), within 10m    |
