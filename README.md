# .github

## Workflow Templates

### Terraform Workflows

the terraform workflow templates require certain branches, these can easily be generated with this script

```sh
branches=(
  "registry"
  "internal-stag"
  "internal-prod"
  "nonpci-stag"
  "nonpci-prod"
  "pci-stag"
  "pci-prod"
)
for t in ${branches[@]}; do
  git switch --orphan "__plan_branch_$t"
  git commit --allow-empty -m "Initial commit on orphan branch"
  git push -u origin "__plan_branch_$t"
done
```
