# Security Policy

This document defines basic security practices for the Craft BD project.

## 1. Sensitive Information

The following information must never be committed to the repository:

- Passwords
- API keys
- Access tokens
- Private keys
- Database credentials
- Payment credentials
- Production secrets
- `.env` files containing sensitive values

## 2. Environment Variables

Sensitive configuration should be stored using environment variables.

Developers may commit an example file such as:

`.env.example`

This file must contain placeholder values only and must never contain real secrets.

## 3. Authentication and Authorization

Authentication and authorization controls must be enforced on the server side.

The system must ensure that users cannot access or modify resources outside their authorized role or ownership.

## 4. Password Storage

Passwords must never be stored as plain text.

A secure password hashing mechanism must be used during implementation.

## 5. Input Validation

All external input must be validated before being processed or stored.

Validation should be applied to:

- Forms
- API requests
- File uploads
- Query parameters
- User-generated content

## 6. Access Control

Craft BD will use role-based access control.

Planned roles:

- Customer
- Artisan
- Administrator

Permissions must be verified on the backend.

## 7. Security Issues

Security-related issues should not expose real credentials, secrets, or sensitive user information.

If a secret is accidentally committed:

1. Revoke or rotate the secret immediately.
2. Remove it from the repository history when necessary.
3. Replace it with secure environment configuration.
4. Review the incident and prevent recurrence.

## 8. Dependencies

Dependencies should be reviewed and updated when security vulnerabilities are identified.

## 9. Data Protection

Sensitive user data should only be collected when necessary for system functionality.

The project should avoid storing unnecessary personal information.

## 10. Security Review

Security requirements will be reviewed again during the dedicated Security & Business Rules phase before production deployment.
