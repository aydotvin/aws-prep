# Section 1:

## AWS Console:

- Always keep a watch on which region an instance is being created. As the instance created in one instance will not show up when another region is selected, but the billing will be happening.
- [AWS Organizations and AWS Account Management Documentation](https://docs.aws.amazon.com/organizations/index.html)

## Global service:

- IAM

---

## Regions, Availability Zones and Edge Locations:

- Cloudfront relies on edge locations.

---

## Securing account:

- Email and password
- MFA
- Access keys - for accessing AWS via terminal and programatically.

### Best practices:

- [Root User](https://docs.aws.amazon.com/accounts/latest/reference/best-practices-root-user.html)
- [Access keys](https://docs.aws.amazon.com/accounts/latest/reference/credentials-access-keys-best-practices.html)

### Access keys:

#### Access key best practices:

- Never store your access key in plain text, in a code repository, or in code.
- Disable or delete access key when no longer needed.
- Enable least-privilege permissions.
- Rotate access keys regularly.

---

## IAM:

- Cannot select regions from IAM console.
- IAM user signin happens via account ID or account alias. These can be found in IAM dashboard.

### User Groups:

#### Why?

- test

---

---
