# Financial Management Platform

## Roles and Responsibilities

### **1. IT Admin**  
**Responsibilities**:  
- **Accounts**:  
  - Create, update, suspend, or delete user accounts.  
  - Ensure system stability and security (e.g., access logs, infrastructure monitoring).
- **Financial Data Access**:  
  - Limited to troubleshooting or audits (e.g., no routine access to investments/transactions).  

---

### **2. Junior Portfolio Manager**  
**Responsibilities**:  
- **Investments**:  
  - Create and manage investments **up to $100,000** in **assigned regions only**.  
  - Approve investments in their region **only if 2FA was completed within the last 10 minutes**.  
- **Transactions**:  
  - Handle transactions within their region and monetary limit ($100,000).  
- **Reports**:  
  - View and run reports **specific to their region and investment threshold**.  
- **Accounts**:  
  - Create or update client accounts **within their assigned regions**.  

---

### **3. Senior Portfolio Manager**  
**Responsibilities**:  
- **Investments**:  
  - Create and manage investments **up to $1,000,000** across **multiple regions**.  
  - Approve investments in any region they manage, **contingent on recent 2FA**.  
- **Transactions**:  
  - Handle transactions across regions, up to $1,000,000.  
- **Reports**:  
  - View, run, and **share reports internally** (e.g., with junior managers or CFO).  
- **Accounts**:  
  - Create or update client accounts across regions.  

---

### **4. End User (Client)**  
**Responsibilities**:  
- **Accounts**:  
  - Update **their own** personal information (e.g., contact details).  
- **Investments/Transactions**:  
  - View **their own** investments and transactions.  
- **Reports**:  
  - View **personalized reports** (no editing or sharing externally unless authorized).  

---

### **5. Chief Financial Officer (CFO)**  
**Responsibilities**:  
- **Full Access**:  
  - View, edit, or delete **any financial data** (accounts, investments, transactions, reports).  
- **Approvals**:  
  - Override transaction/investment approvals **without regional or monetary restrictions**.  
- **Audits**:  
  - Access audit logs and compliance reports.  
- **Sharing**:  
  - Share reports **externally** (e.g., with regulators or board members).  

---

### **Key Conditions Applied to Roles**:  
1. **Ownership/Assignment**:  
   - Users and managers can only access resources they **own** or are **assigned to** (e.g., regions, accounts).  
2. **Monetary Thresholds**:  
   - Junior: ≤ $100,000 | Senior: ≤ $1,000,000.  
3. **Security Requirements**:  
   - Sensitive actions (e.g., approvals) require **2FA within 10 minutes**.  
4. **Time-Based Restrictions**:  
   - Canceling transactions is allowed **only within 2 hours** of creation.

---

### **1. Resource: Accounts**  
**Actions**:  
- **Create**: IT Admin, CFO, Portfolio Managers (Junior/Senior).  
- **Update**:  
  - *Owners*: Regular users (their own info).  
  - *Admins*: IT Admin, CFO, Portfolio Managers (client account details).  
- **Suspend/Delete**: IT Admin, CFO.  
- **View**:  
  - *Owners*: Regular users (their own accounts).  
  - *Admins*: IT Admin, CFO, Portfolio Managers (all client accounts).  

**Conditions**:  
- Regular users can **only update their own data** (ownership restriction).  
- Portfolio Managers can only manage accounts in **their assigned regions** (junior) or **all regions** (senior).  

---

### **2. Resource: Investments**  
**Actions**:  
- **Create**: Portfolio Managers (Junior/Senior), CFO.  
- **Update**: Portfolio Managers (Junior/Senior), CFO.  
- **Approve**:  
  - *Portfolio Managers*: Only if assigned to the investment’s region and **2FA completed within 10 minutes**.  
  - *CFO*: Unrestricted.  
- **Delete**: CFO.  
- **View**:  
  - *Owners*: Regular users (their own investments).  
  - *Portfolio Managers*: Investments in assigned regions.  
  - *CFO*: All investments.  

**Conditions**:  
- **Monetary thresholds**:  
  - Junior: ≤ $100,000.  
  - Senior: ≤ $1,000,000.  
- **Regional restrictions**: Junior managers limited to assigned regions; seniors can operate across regions.  

---

### **3. Resource: Reports**  
**Actions**:  
- **Run**: Portfolio Managers (region-specific), CFO.  
- **View**:  
  - *Owners*: Regular users (their own reports).  
  - *Portfolio Managers*: Reports for their regions and investment thresholds.  
  - *CFO*: All reports.  
- **Edit**: CFO, Senior Portfolio Managers (internal edits only).  
- **Share**:  
  - *Internally*: Portfolio Managers (Senior), CFO.  
  - *Externally*: CFO (requires additional approval for sensitive data).  
- **Delete**: CFO.  

**Conditions**:  
- External sharing requires **explicit authorization** (e.g., encryption or client consent).  

---

### **4. Resource: Transactions**  
**Actions**:  
- **Create**: Portfolio Managers (Junior/Senior), CFO.  
- **Update**: Portfolio Managers (Junior/Senior), CFO.  
- **Approve**:  
  - *Portfolio Managers*: Requires **2FA within 10 minutes** and regional assignment.  
  - *CFO*: No restrictions.  
- **Cancel**:  
  - *Portfolio Managers*: Within **2 hours** of creation.  
  - *CFO*: Unrestricted.  
- **View**:  
  - *Owners*: Regular users (their own transactions).  
  - *Portfolio Managers*: Transactions in assigned regions.  
  - *CFO*: All transactions.  
- **Delete**: CFO.  

**Conditions**:  
- **Monetary thresholds**: Same as investments (Junior ≤ $100k, Senior ≤ $1M).  
- **Time-based cancellation**: Limited to 2-hour window.  

---

### **Summary of Key Conditions**:  
| **Condition Type**       | **Examples**                                                                 |  
|--------------------------|-----------------------------------------------------------------------------|  
| **Ownership**            | Users can only act on resources they own (e.g., their accounts, investments). |  
| **Regional Assignment**  | Junior managers restricted to assigned regions; seniors can cross regions.    |  
| **Monetary Thresholds**  | Junior: ≤ $100k; Senior: ≤ $1M; CFO: No limits.                      |  
| **Security (2FA)**       | Required for approving investments/transactions (valid within 10 minutes).    |  
| **Time Restrictions**    | Canceling transactions allowed only within 2 hours of creation.               |  

---

## RBAC matrix:

---

### **1. Accounts**  
| **Action**         | **IT Admin** | **Junior PM**        | **Senior PM**       | **End User** | **CFO** |  
|--------------------|--------------|----------------------|---------------------|--------------|---------|  
| Create             | ✅           | ✅ (assigned region) | ✅ (all regions)    | ❌           | ✅      |  
| Update (own)       | ❌           | ❌                   | ❌                  | ✅           | ❌      |  
| Update (others)    | ✅           | ✅ (assigned region) | ✅ (all regions)    | ❌           | ✅      |  
| Suspend/Delete     | ✅           | ❌                   | ❌                  | ❌           | ✅      |  
| View               | ✅ (all)     | ✅ (assigned region) | ✅ (all regions)    | ✅ (own)     | ✅      |  

**Conditions**:  
- Junior/Senior PMs can only manage client accounts in their **assigned regions** (Junior) or **all regions** (Senior).  
- End Users can only update/view their own accounts.  

---

### **2. Investments**  
| **Action**         | **IT Admin** | **Junior PM**                     | **Senior PM**                    | **End User** | **CFO** |  
|--------------------|--------------|-----------------------------------|----------------------------------|--------------|---------|  
| Create             | ❌           | ✅ (≤ $100k, assigned region)     | ✅ (≤ $1M, all regions)          | ❌           | ✅      |  
| Update             | ❌           | ✅ (≤ $100k, assigned region)     | ✅ (≤ $1M, all regions)          | ❌           | ✅      |  
| Approve            | ❌           | ✅ (assigned region + 2FA*)       | ✅ (any region + 2FA*)           | ❌           | ✅      |  
| Delete             | ❌           | ❌                                | ❌                               | ❌           | ✅      |  
| View               | ❌           | ✅ (assigned region)              | ✅ (all regions)                 | ✅ (own)     | ✅      |  

**Conditions**:  
- **Monetary thresholds**: Junior ($100k), Senior ($1M).  
- **2FA**: Required for approvals (*valid within 10 minutes*).  

---

### **3. Reports**  
| **Action**         | **IT Admin** | **Junior PM**        | **Senior PM**       | **End User** | **CFO** |  
|--------------------|--------------|----------------------|---------------------|--------------|---------|  
| Run                | ❌           | ✅ (assigned region) | ✅ (all regions)     | ❌           | ✅      |  
| View               | ❌           | ✅ (assigned region) | ✅ (all regions)     | ✅ (own)     | ✅      |  
| Edit               | ❌           | ❌                   | ✅ (internal only)   | ❌           | ✅      |  
| Share (internal)   | ❌           | ❌                   | ✅                   | ❌           | ✅      |  
| Share (external)   | ❌           | ❌                   | ❌                   | ❌           | ✅      |  
| Delete             | ❌           | ❌                   | ❌                   | ❌           | ✅      |  

**Conditions**:  
- External report sharing requires **CFO approval** and encryption.  

---

### **4. Transactions**  
| **Action**         | **IT Admin** | **Junior PM**                     | **Senior PM**                    | **End User** | **CFO** |  
|--------------------|--------------|-----------------------------------|----------------------------------|--------------|---------|  
| Create             | ❌           | ✅ (≤ $100k, assigned region)     | ✅ (≤ $1M, all regions)          | ❌           | ✅      |  
| Update             | ❌           | ✅ (≤ $100k, assigned region)     | ✅ (≤ $1M, all regions)          | ❌           | ✅      |  
| Approve            | ❌           | ✅ (assigned region + 2FA*)       | ✅ (any region + 2FA*)           | ❌           | ✅      |  
| Cancel             | ❌           | ✅ (within 2 hours)               | ✅ (within 2 hours)              | ❌           | ✅      |  
| View               | ❌           | ✅ (assigned region)              | ✅ (all regions)                 | ✅ (own)     | ✅      |  

**Conditions**:  
- **Cancellation**: Allowed only within **2 hours** of transaction creation.  
- **2FA**: Required for approvals (*valid within 10 minutes*).
  
