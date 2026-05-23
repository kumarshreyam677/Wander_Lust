# WanderLust - Full-Stack Accommodation Marketplace

A marketplace platform enabling users to browse, list, and review vacation accommodations with secure authentication, detailed property information, and user feedback systems.

**[🌐 Live Demo](https://wander-lust-o71i.onrender.com/listings)** | **[📂 GitHub Repository](https://github.com/kumarshreyam677/Wander_Lust)**

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Screenshots](#screenshots)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Key Implementation Details](#key-implementation-details)
- [Learning Outcomes](#learning-outcomes)

---

## ✨ Features

### User Authentication & Authorization
- **Secure Registration & Login** - Passport.js local authentication with bcrypt password hashing
- **Session Management** - Persistent sessions via connect-mongo for user state management
- **Protected Routes** - Middleware-based authorization for user-specific operations
- **User Dashboard** - "Your home" section to manage personal listings

### Listing Management (CRUD Operations)
- **Create Listings** - Users can add new accommodation properties with detailed information and images
- **Browse Listings** - View all available properties with filtering by categories (Trending, Rooms, Iconic Cities, Mountains, etc.)
- **View Details** - See complete listing information including title, description, price, location, and owner details
- **Update Listings** - Modify existing property details and upload new images
- **Delete Listings** - Remove listings with cascading deletion of associated reviews

### Advanced Features
- **Image Upload & Management** - Cloudinary CDN integration for optimized image storage and compression
- **Geolocation Mapping** - Mapbox API integration to display properties on interactive maps
- **Nested Reviews System** - Users can leave reviews on listings with ratings and comments
- **Category Filtering** - Browse listings by predefined categories (Rooms, Mountains, Castles, Amazing Pools, etc.)
- **Search Functionality** - Search destinations with real-time filtering
- **Input Validation** - Server-side Joi validation for data integrity and security
- **Responsive Design** - EJS templating with mobile-friendly interface

---

## 🛠️ Tech Stack

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** Passport.js (Local Strategy)
- **Validation:** Joi
- **Session Management:** connect-mongo
- **Password Hashing:** bcrypt

### Frontend
- **Template Engine:** EJS
- **Styling:** CSS3 (Responsive Design)
- **Interactive Maps:** Mapbox GL JS

### Cloud & External Services
- **Image Storage:** Cloudinary + Multer (File Upload Middleware)
- **Geolocation:** Mapbox API
- **Deployment:** Render

---

## 📸 Screenshots

### 1. Explore/Homepage - Browse Listings
<img width="1710" height="986" alt="Screenshot 2026-05-23 at 3 32 00 PM" src="https://github.com/user-attachments/assets/370363f9-bc8a-4bf1-bec0-db3bbd0964a2" />

- Dashboard showing property cards with images, titles, and pricing
- Category filters: Trending, Rooms, Iconic Cities, Mountains, Castles, Amazing Pools, Camping, Farms, Arctic, Domes, Boats
- Search destination functionality
- "Display total after taxes" toggle option
- User authentication state in navigation (Your home, Log Out)

### 2. Listing Detail Page - Complete Property Information
<img width="1710" height="986" alt="Screenshot 2026-05-23 at 3 33 36 PM" src="https://github.com/user-attachments/assets/098d0875-e774-484f-8745-8d95d0619b8a" />

- Full property image gallery (Cloudinary optimized)
- Complete listing details: Title, Price, Description, Location (Country)
- Owner information ("Owned By: bsdk")
- Edit & Delete buttons (for property owners)
- **Leave a Review** section with:
  - 5-star rating system
  - Comments text area
  - Submit review functionality
- Nested review display showing all user reviews

### 3. Create New Listing - Property Addition Form
<img width="1710" height="986" alt="Screenshot 2026-05-23 at 3 34 07 PM" src="https://github.com/user-attachments/assets/68b192e0-73d4-414b-ac6e-334721e09f06" />

- Form fields:
  - **Title** - Property name/heading
  - **Description** - Detailed property information
  - **Upload Listing Image** - File upload with Cloudinary integration
  - **Price** - Nightly rate
  - **Country** - Property location
  - **Location** - Specific address (with Mapbox geocoding)
- Form validation with error handling
- Clean, intuitive UI with clear field labels

### 4. Edit Listing - Modify Property Details
<img width="1710" height="986" alt="Screenshot 2026-05-23 at 3 34 29 PM" src="https://github.com/user-attachments/assets/50831fe3-4abe-4399-ba2a-60a3ab52c957" />

- Pre-populated form with existing listing data
- Display original image with option to update
- **Upload New Image** - Replace property photo
- All fields editable: Title, Description, Price, Country, Location
- Edit button to submit changes
- Demonstrates READ and UPDATE operations in CRUD cycle

---

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (Local or Atlas Cloud)
- Cloudinary Account (Free tier available)
- Mapbox Account (Free tier available)
- npm or yarn package manager

### Step 1: Clone the Repository
```bash
git clone https://github.com/kumarshreyam677/Wander_Lust.git
cd Wander_Lust
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Configure Environment Variables
Create a `.env` file in the root directory and add:
```env
PORT=3000
MONGODB_URL=your_mongodb_connection_string
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_KEY=your_cloudinary_api_key
CLOUDINARY_SECRET=your_cloudinary_api_secret
MAPBOX_TOKEN=your_mapbox_access_token
SESSION_SECRET=your_session_secret_key
NODE_ENV=development
```

**How to get these credentials:**
- **MongoDB:** Create account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas), create cluster, get connection string
- **Cloudinary:** Sign up at [Cloudinary](https://cloudinary.com), go to Dashboard, copy Cloud Name, API Key, API Secret
- **Mapbox:** Register at [Mapbox](https://www.mapbox.com), create access token in Account settings
- **SESSION_SECRET:** Generate any random string (e.g., `your-secret-key-12345`)

### Step 4: Run the Application Locally
```bash
npm start
```

The application will start at `http://localhost:3000`

### Step 5: Access the Live Demo
Visit the deployed version: **[https://wander-lust-o71i.onrender.com/listings](https://wander-lust-o71i.onrender.com/listings)**

---

## 💻 Usage

### For New Users

1. **Register Account**
   - Click on "Log Out" area → Sign Up
   - Enter email, password, confirm password
   - Account created with secure password hashing (bcrypt)
   - Automatic redirect to login

2. **Login**
   - Enter email and password
   - Session created and maintained via connect-mongo
   - Access to personalized features (your listings, create new listing)

3. **Browse Listings**
   - View homepage with featured properties
   - Use category filters (Rooms, Mountains, etc.)
   - Click on property card to view full details
   - Read reviews from other users
   - View property location on interactive Mapbox

4. **Create a Listing**
   - Click "WanderLust your home" in navigation
   - Fill in property details:
     - **Title:** Property name
     - **Description:** Detailed information about the property
     - **Image:** Upload photo (stored in Cloudinary)
     - **Price:** Per-night cost
     - **Country:** Nation location
     - **Location:** City/address (geocoded with Mapbox)
   - Click "Add" to publish listing
   - Listing appears on platform for other users to discover

5. **Leave Reviews**
   - Open any listing detail page
   - Scroll to "Leave a Review" section
   - Select star rating (1-5 stars)
   - Write comment/feedback
   - Submit review
   - Review appears in nested reviews section

6. **Manage Your Listings**
   - Navigate to "Your home" → Your listings
   - View all your published properties
   - Click "Edit" to modify listing details
   - Click "Delete" to remove listing
   - All associated reviews automatically deleted (cascading delete)

---

## 📁 Project Structure

```
Wander_Lust/
├── models/
│   ├── listing.js              # Listing schema with image/location fields
│   ├── review.js               # Nested review schema
│   └── user.js                 # User authentication schema with password hash
├── routes/
│   ├── listing.js              # CRUD routes for listings (/listings GET/POST/PUT/DELETE)
│   ├── review.js               # Review routes (nested under listings)
│   └── user.js                 # Auth routes (/login, /register, /logout)
├── controllers/
│   ├── listingController.js    # Business logic for listing operations
│   ├── reviewController.js     # Review logic and validation
│   └── userController.js       # Authentication logic
├── views/
│   ├── listings/
│   │   ├── index.ejs          # Main browse/explore page
│   │   ├── show.ejs           # Listing detail page
│   │   ├── new.ejs            # Create listing form
│   │   └── edit.ejs           # Edit listing form
│   ├── auth/
│   │   ├── login.ejs          # Login page
│   │   └── register.ejs       # Registration page
│   ├── layouts/
│   │   └── boilerplate.ejs    # Main layout template
│   └── reviews/
│       └── form.ejs           # Review form (nested)
├── middleware/
│   ├── auth.js                # isLoggedIn, isOwner middleware
│   ├── validation.js          # Joi schema validation middleware
│   └── errorHandler.js        # Centralized error handling
├── config/
│   ├── cloudinary.js          # Cloudinary storage configuration (multer)
│   ├── database.js            # MongoDB connection
│   └── passport.js            # Passport strategy setup
├── public/
│   ├── css/
│   │   └── style.css          # Global styles, responsive design
│   ├── js/
│   │   └── mapbox-init.js     # Mapbox initialization script
│   └── images/                # Static assets
├── .env.example               # Environment variables template
├── .gitignore                 # Git ignore configuration
├── app.js                     # Express application setup
├── server.js                  # Server entry point
├── package.json               # Dependencies and scripts
└── README.md                  # Project documentation
```

---

## 🔧 Key Implementation Details

### 1. Authentication Architecture (Passport.js + Sessions)
```
┌─────────────────────────────────────────────────────────┐
│ User Registration                                        │
│ 1. User fills register form (email, password)          │
│ 2. Password hashed with bcrypt (salt rounds: 12)       │
│ 3. User document created in MongoDB                    │
│ 4. Redirect to login                                   │
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ User Login                                              │
│ 1. Passport.js verifies email & hashed password        │
│ 2. Session created and stored in MongoDB               │
│ 3. Session ID sent as cookie to client                 │
│ 4. Redirect to authenticated home                      │
└─────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────┐
│ Protected Routes                                        │
│ 1. Middleware checks session existence                 │
│ 2. If valid → Allow access to user-specific routes     │
│ 3. If invalid → Redirect to login                      │
└─────────────────────────────────────────────────────────┘
```

### 2. Listing CRUD Operations (RESTful Design)
```
CREATE:  POST   /listings              → Form → Cloudinary upload → MongoDB save
READ:    GET    /listings              → All listings from DB → Render
         GET    /listings/:id          → Single listing with reviews
UPDATE:  PUT    /listings/:id          → Edit form → Cloudinary update → DB update
DELETE:  DELETE /listings/:id          → Remove from DB → Cascade delete reviews
```

### 3. Image Upload Pipeline (Cloudinary + Multer)
```
User selects image file
         ↓
Multer middleware validates & processes
         ↓
Image sent to Cloudinary API
         ↓
Cloudinary stores + optimizes + returns secure URL
         ↓
URL saved in MongoDB listing document
         ↓
EJS template loads image from CDN (fast, optimized)
```

### 4. Nested Reviews with Data Integrity (Cascading Delete)
```
Listing Document (parent)
├─ Review 1 (child) → user, rating, comment, createdAt
├─ Review 2 (child) → user, rating, comment, createdAt
├─ Review 3 (child) → user, rating, comment, createdAt
└─ Review 4 (child) → user, rating, comment, createdAt

When listing is deleted:
  → Mongoose findByIdAndDelete() triggers pre-hook
  → All nested reviews automatically removed
  → Database consistency maintained (no orphaned data)
```

### 5. Geolocation Mapping (Mapbox Integration)
```
User enters address in location field
         ↓
Form submission → Mapbox Geocoding API
         ↓
Address converted to latitude/longitude coordinates
         ↓
Coordinates stored in MongoDB listing document
         ↓
On detail page → Mapbox GL JS renders interactive map
         ↓
User sees property pinned on map for context
```

### 6. Input Validation (Joi + Express Middleware)
```
User submits form data
         ↓
Joi schema validates:
  - Title: string, required, min length
  - Description: string, required
  - Price: number, positive, required
  - Image: file, image type only
  - Location: string, required
         ↓
If validation fails → Error message → Re-render form
If validation passes → Process request → Save to DB
```

---

## 🎓 Learning Outcomes

This project demonstrates proficiency in:

### Backend Development
- ✅ **RESTful API Design** - Proper HTTP methods, status codes, and endpoint structure
- ✅ **Express.js Fundamentals** - Routing, middleware, request-response cycle
- ✅ **Error Handling** - Centralized error handling, validation errors, async/await error catching
- ✅ **Stateful Applications** - Session management and user persistence

### Database Design
- ✅ **MongoDB Schema Design** - Document structure, relationships, indexing
- ✅ **Mongoose ODM** - Model definition, validation, hooks (pre/post)
- ✅ **Nested Relationships** - Parent-child document relationships
- ✅ **Data Integrity** - Cascading operations, referential integrity patterns

### Authentication & Security
- ✅ **User Authentication** - Passport.js local strategy implementation
- ✅ **Password Security** - Bcrypt hashing, salt rounds, secure comparison
- ✅ **Session Management** - connect-mongo for persistent user sessions
- ✅ **Authorization** - Protected routes, ownership verification, middleware-based access control
- ✅ **Input Sanitization** - Joi validation to prevent injection attacks

### Third-Party Integration
- ✅ **Cloudinary API** - Image upload, storage, optimization, CDN delivery
- ✅ **Mapbox API** - Geocoding, coordinate transformation, interactive map rendering
- ✅ **Multer Middleware** - File upload handling, validation, storage configuration
- ✅ **External Service Management** - API keys, error handling, retry logic

### Full-Stack Development
- ✅ **EJS Templating** - Server-side rendering, dynamic content, form handling
- ✅ **Responsive Design** - CSS layouts, mobile-friendly interface
- ✅ **Frontend-Backend Communication** - Form submissions, AJAX if applicable
- ✅ **Production Deployment** - Render, environment variables, database hosting

### Software Engineering Practices
- ✅ **Code Organization** - MVC pattern, separation of concerns
- ✅ **Debugging & Testing** - Console logging, browser dev tools, postman API testing
- ✅ **Version Control** - Git workflows, commit history
- ✅ **Documentation** - README, code comments, project structure clarity

---

## 🚀 Deployment Information

**Platform:** Render (Cloud Application Hosting)

**Deployment Stack:**
- Frontend: EJS templates served by Express
- Backend: Node.js runtime on Render
- Database: MongoDB Atlas (Cloud)
- File Storage: Cloudinary CDN
- Maps: Mapbox (Hosted)

**Live URL:** [https://wander-lust-o71i.onrender.com/listings](https://wander-lust-o71i.onrender.com/listings)

---

## 📝 Future Enhancements

- [ ] Advanced search and filtering (price range, amenities, rating, review count)
- [ ] User profile page with profile picture and bio
- [ ] Listing management dashboard with analytics
- [ ] Email notifications (welcome, booking confirmation, review notifications)
- [ ] Payment integration (Stripe/Razorpay for bookings)
- [ ] Booking/Reservation system with calendar
- [ ] Host ratings and verification badge system
- [ ] Real-time notifications using WebSockets (Socket.io)
- [ ] Performance optimization (database indexing, caching, lazy loading)
- [ ] Image gallery with carousel slider
- [ ] Wishlist/Favorites feature
- [ ] Advanced map features (clustering, filtering by map bounds)

---

## 🔗 Important Links

- **Live Application:** [https://wander-lust-o71i.onrender.com/listings](https://wander-lust-o71i.onrender.com/listings)
- **GitHub Repository:** [https://github.com/kumarshreyam677/Wander_Lust](https://github.com/kumarshreyam677/Wander_Lust)
- **Cloudinary Docs:** [https://cloudinary.com/documentation](https://cloudinary.com/documentation)
- **Mapbox Docs:** [https://docs.mapbox.com](https://docs.mapbox.com)
- **Passport.js Guide:** [http://www.passportjs.org](http://www.passportjs.org)

---

## 📧 Questions & Support

For questions, issues, or suggestions:
- Open an Issue on [GitHub](https://github.com/kumarshreyam677/Wander_Lust/issues)
- Review commit history for development journey
- Check individual files for implementation details

---

## 📄 License

This project is open source and available under the MIT License.

---

**Built with ❤️ using Node.js, Express, MongoDB, Cloudinary, and Mapbox**

**Author:** Shreyam Kumar

**Repository:** [github.com/kumarshreyam677/Wander_Lust](https://github.com/kumarshreyam677/Wander_Lust)
