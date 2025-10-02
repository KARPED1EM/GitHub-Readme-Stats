
# GitHub Readme Stats — Extended Fork

This is a customized fork of  
👉 [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats)

---

## 📖 About This Fork

The original **GitHub Readme Stats** generates beautiful cards for your GitHub profile.  
This fork, with the help of **GPT‑5**, extends its functionality to allow **finer control** over which repositories and organizations are included in your stats.

---

## 🚀 New Features

### 1. Role Parameter
Control which repository affiliations are counted in statistics.

- **Parameter:** `role`
- **Allowed values:**  
  - `OWNER`  
  - `COLLABORATOR`  
  - `ORGANIZATION_MEMBER`
- **Default:** `OWNER`
- **Usage:** values can be combined with commas

Example:  
```
/api?username=yourname&role=OWNER,COLLABORATOR,ORGANIZATION_MEMBER
```

---

### 2. Repository & Organization Filters

| Parameter | Purpose | Notes | Example |
|-----------|---------|-------|---------|
| `exclude_repo` | Exclude specific repositories by name | Highest priority | `exclude_repo=repo1,repo2` |
| `exclude_org` | Exclude entire organizations by login | Applied after repo filter | `exclude_org=myorg1,myorg2` |
| `exclude_org_whitelist_repo` | Allow specific repos from excluded orgs | Acts as exception list | `exclude_org=myorg&exclude_org_whitelist_repo=myorg-core,myorg-utils` |

**Priority order:**  
1. `exclude_repo`  
2. `exclude_org`  
3. `exclude_org_whitelist_repo` (can override org exclusion)

---

## 🖼 Examples

**Stats Card (include org repos but exclude one organization):**
```
[Stats](https://your-vercel-domain.vercel.app/api?username=yourname&role=OWNER,COLLABORATOR,ORGANIZATION_MEMBER&exclude_org=myorg)
```

**Top Languages Card (exclude org but whitelist 1 repo):**
```
[Top Langs](https://your-vercel-domain.vercel.app/api/top-langs?username=yourname&role=OWNER,COLLABORATOR,ORGANIZATION_MEMBER&exclude_org=myorg&exclude_org_whitelist_repo=myorg-core)
```

---

## ⚠️ Notes & Limitations

- **GitHub API limits:** These stats are based on repositories you *own* or *are affiliated with*, not strictly on contribution history.  
- Ensure your **Personal Access Token (PAT)** includes the necessary scope to read organization repositories if you use `role=ORGANIZATION_MEMBER`.  
- If you experience unexpected high numbers of stars, check that you have not included popular organizations by mistake. Use the exclusion parameters to fine‑tune results.  

---

## 🔗 Credits

- Original project: [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats)  
- Extended logic & code generation assisted by: **GPT‑5**

---