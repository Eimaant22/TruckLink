# TruckLink — Driver Hiring & Onboarding Portal (Backend)

TruckLink is a role-based web platform for the trucking industry that connects drivers looking for work with recruiters looking to fill open positions, with a platform admin moderating every driver profile before it goes live. This repository contains the **backend** of the project, which I built independently.

## 🔗 Live Demo

(https://trucklink-frontend-u8wd-git-main-duamalik.vercel.app/)

## 🔗 Backend Repository

[https://github.com/Eimaant22/TruckLink/]

## 🔗 Frontend Repository

[Add frontend repository link here]

## 🚀 My Contribution (Backend)

- Built the backend API using **NestJS**
- Designed and managed the database schema using **PostgreSQL**
- Implemented **JWT-based role authentication** for three distinct roles: Driver, Recruiter, and Admin
- Added route/permission guards so each role only accesses what it's meant to (e.g. recruiters never see unapproved driver profiles)
- Developed the core backend workflows:
  - **Driver Profiles** — structured profile creation (personal info, CDL class, endorsements, experience, equipment type, availability), document upload, and profile status tracking (Pending / Approved / Rejected) with timestamped status history
  - **Moderation** — admin moderation queue to review, approve, reject, or request changes on driver profiles, with comments/reasons
  - **Recruiter & Job Postings** — recruiter account and company profile management, posting driving positions with requirements (endorsements, experience, route type, location, equipment)
  - **Matching** — rule-based filtering that returns only approved drivers matching a recruiter's posted requirements
  - **Admin Controls** — recruiter account approval/suspension, and management of master data (endorsement types, equipment types, regions)
  - **File Storage** — document uploads (license, medical card) handled via cloud/S3-compatible storage

## 🛠️ Tech Stack

- **Backend:** NestJS (Node.js)
- **Database:** PostgreSQL
- **Authentication:** JWT (role-based)
- **Real-time:** Socket.io (for live status/match notifications)
- **File Storage:** S3-compatible cloud bucket
- **Frontend:** React / Next.js (built separately — see link above)

## 👥 User Roles

| Role | Core Capabilities |
|------|-------------------|
| **Driver** | Sign up, build profile, track approval status, browse/apply to matching opportunities |
| **Driver Recruiter** | Sign up, post job requirements, view/filter matching approved drivers, shortlist or contact them |
| **Platform Admin** | Review and moderate driver profiles, manage recruiter accounts, manage master data, view platform analytics |

## ⚙️ Getting Started

1. Clone this repository
   ```bash
   git clone (https://github.com/Eimaant22/TruckLink/)
   cd TruckLink-Backend
   ```
2. Install dependencies
   ```bash
   npm install
   ```
3. Create a `.env` file with the following variables:
   ```env
   PORT=5000
   DATABASE_URL=your_postgresql_connection_string
   JWT_SECRET=your_jwt_secret
   AWS_ACCESS_KEY_ID=your_s3_access_key
   AWS_SECRET_ACCESS_KEY=your_s3_secret_key
   AWS_BUCKET_NAME=your_bucket_name
   ```
4. Run database migrations (if applicable)
   ```bash
   npm run migration:run
   ```
5. Start the development server
   ```bash
   npm run start:dev
   ```
   The API will be available at `http://localhost:5000`.
