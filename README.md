# Video Submission Guide - INFT4000 Assignment 1
**Student**: Mahitkc  
**Course**: INFT4000 - Fall 2025/2026  
**Assignment**: Prompt Engineering - Cafe Manager API

## 📋 Video Recording Checklist

### 1. PROJECT REQUIREMENTS DOCUMENT (PRD)

#### ☐ API Endpoints PRD
**File to Show**: `API-PRD.md`
**Lines to Highlight**: 
- Lines 1-20: Introduction and overview
- Lines 85-120: Menu Items endpoints
- Lines 150-180: Customers endpoints  
- Lines 210-240: Orders endpoints
- Lines 270-300: Authentication and error handling

**What to Say**: 
"Here's my API PRD document showing all the endpoints I've defined for the Cafe Manager API, including full CRUD operations for menu items, customers, and orders."

#### ☐ Data Models
**File to Show**: `API-PRD.md`
**Lines to Highlight**:
- Lines 45-84: Data models section
- Show MenuItem, Customer, Order schemas

**What to Say**:
"These are the data models I've defined with proper validation rules, data types, and relationships between entities. You can see the MenuItem model has required fields like name, price, and category, with proper data types. The Customer model includes contact information with email validation. The Order model establishes relationships between customers and menu items with quantity tracking."

#### ☐ Expected Behaviors  
**File to Show**: `API-PRD.md`
**Lines to Highlight**:
- Lines 300-350: Business logic and validation rules
- Error handling specifications

**What to Say**:
"Here I've documented the expected behaviors including validation rules, error handling patterns, and business logic. For example, menu items must have positive prices, customers need valid email formats, and orders require both a customer and at least one menu item. The error responses follow REST conventions with proper HTTP status codes."

---

### 2. SOURCE CODE DEMONSTRATION

#### ☐ Backend REST API with Full CRUD Operations

**Terminal Commands to Run**:
```bash
# Line 1: Navigate to project
cd cafe-manager-api

# Line 2: Start the server
node server.js
```

**Files to Show**:
1. **Server Entry Point**: `server.js` (Lines 1-50)
2. **Route Definitions**: 
   - `src/routes/menuItems.js` (Lines 1-344)
   - `src/routes/customers.js` (Lines 1-280)
   - `src/routes/orders.js` (Lines 1-320)
3. **Controllers**:
   - `src/controllers/menuItemController.js` (Lines 1-200)
   - `src/controllers/customerController.js` (Lines 1-150)
   - `src/controllers/orderController.js` (Lines 1-180)

**What to Demonstrate**:
- Show server starting with database connection
- Navigate through code structure
- Highlight CRUD operations in each controller

**What to Say**:
"Let me start the server to show you the API in action. As you can see, the server starts successfully and connects to the SQLite database. The project follows a clean MVC architecture - here are the routes that define our endpoints, the controllers that contain our business logic, and the models that handle data operations. Each controller implements full CRUD functionality - Create, Read, Update, and Delete operations for menu items, customers, and orders."

#### ☐ Code Structure and Organization

**Files to Show**:
1. **Project Structure**: Show folder tree
2. **Configuration**: `src/config/` folder
3. **Models**: `src/models/` folder  
4. **Middleware**: `src/middleware/` folder
5. **Database Scripts**: `scripts/` folder

**What to Say**:
"The code follows MVC architecture with clear separation of concerns - routes, controllers, models, and middleware are all organized in separate folders. In the config folder, I have database and Swagger configurations. The middleware includes error handling, logging, and validation. The models contain both SQLite and MySQL implementations for flexibility. The scripts folder has database setup and migration tools."

#### ☐ README File with Setup Instructions

**File to Show**: `README.md`
**Lines to Highlight**:
- Lines 1-30: Project description
- Lines 35-80: Installation and setup steps
- Lines 85-120: API usage examples
- Lines 125-150: Deployment instructions

**What to Say**:
"The README provides comprehensive documentation for the project. It starts with a clear description of what the Cafe Manager API does, followed by step-by-step installation instructions. I've included API usage examples for all major operations, and there are detailed deployment instructions for both local development and production environments."

---

### 3. PROMPT LOG DEMONSTRATION

#### ☐ Prompt Log Examples

**File to Show**: `PROMPT_LOG.md`
**Lines to Highlight**:

**Ask Mode Examples** (Lines 50-120):
- "How do I create a REST API with Express.js?"
- "What's the best way to structure a Node.js project?"
- "How do I implement JWT authentication?"

**What to Say for Ask Mode**:
"In Ask mode, I used AI to get guidance on best practices and architectural decisions. For example, I asked about REST API design patterns, project structure recommendations, and authentication strategies."

**Edit Mode Examples** (Lines 150-250):
- Code generation prompts
- File modification requests
- Database schema creation

**What to Say for Edit Mode**:
"Edit mode was used for specific code modifications and file creation. I would provide context about what I needed and the AI would generate or modify the exact code files."

**Agent Mode Examples** (Lines 280-350):
- "Create a complete CRUD API for menu items"
- "Set up Swagger documentation"
- "Deploy the API to Render"

**What to Say for Agent Mode**:
"Agent mode was the most powerful for complex tasks. I could ask for complete feature implementations like the entire CRUD API, Swagger documentation setup, or deployment configurations."

#### ☐ Reflection on Effective Prompts

**Lines to Show**: 400-500 in `PROMPT_LOG.md`
**What to Say**:
"The most effective prompts were specific and included context. For example, asking for 'a complete CRUD API with validation' worked better than just 'create an API'. I learned that providing clear requirements, expected file structures, and specific technologies led to much better results. The AI performed best when I gave it examples of what I wanted and clear acceptance criteria."

---

### 4. API DOCUMENTATION & DEVELOPMENT

#### ☐ Swagger Documentation in Browser

**Steps to Demonstrate**:
1. **Start Server**: Ensure `node server.js` is running
2. **Open Browser**: Navigate to `http://localhost:3000/api-docs`
3. **Show Documentation**: 
   - API title and version
   - All endpoint categories
   - Request/response schemas
   - Example payloads

**What to Say**:
"Here's the interactive Swagger documentation generated automatically from my API code comments. It shows all available endpoints with example requests and responses. You can see we have three main sections - Menu Items, Customers, and Orders. Each endpoint shows the HTTP method, required parameters, request body schemas, and possible response codes. This makes the API self-documenting and easy for other developers to understand and use."

#### ☐ Deployed API

**URL to Show**: `https://your-app-name.onrender.com`
**Files to Reference**:
- `RENDER_DEPLOYMENT.md` (Lines 1-100)
- `render.yaml` (Lines 1-20)

**What to Demonstrate**:
- Live API health check: `https://your-app.onrender.com/health`
- Live Swagger docs: `https://your-app.onrender.com/api-docs`

**What to Say**:
"The API is deployed and running live on Render. Here's the health check endpoint showing the API is operational with database connectivity. The live Swagger documentation is also available, allowing anyone to test the API endpoints directly from the browser without needing to set up a local environment."

#### ☐ Testing Endpoints

**Method 1: Swagger UI Testing**
1. **Open**: `http://localhost:3000/api-docs`
2. **Test GET**: Click "GET /api/v1/menuItems" → "Try it out" → "Execute"
3. **Test POST**: Click "POST /api/v1/menuItems" → Add JSON:
```json
{
  "name": "Cappuccino",
  "description": "Rich espresso with steamed milk foam",
  "price": 4.50,
  "category": "Beverages"
}
```
4. **Test PUT**: Update the created item
5. **Test DELETE**: Remove the item

**What to Say for Swagger Testing**:
"Let me demonstrate API testing through the Swagger interface. First, I'll test the GET endpoint to retrieve all menu items. Now I'll create a new item by posting this JSON data - notice how Swagger shows the request format and validates the response. I can also test PUT for updates and DELETE for removal, all with immediate feedback."

**Method 2: Terminal cURL Commands**
```bash
# GET request
curl -X GET "http://localhost:3000/api/v1/menuItems"

# POST request  
curl -X POST "http://localhost:3000/api/v1/menuItems" \
  -H "Content-Type: application/json" \
  -d '{"name":"Latte","price":4.25,"category":"Beverages"}'

# PUT request
curl -X PUT "http://localhost:3000/api/v1/menuItems/1" \
  -H "Content-Type: application/json" \
  -d '{"price":4.75}'

# DELETE request
curl -X DELETE "http://localhost:3000/api/v1/menuItems/1"
```

**What to Say for Terminal Testing**:
"I can also test the API using terminal commands with cURL. This demonstrates that the API works with any HTTP client, not just the browser interface. Here's a GET request returning all menu items in JSON format. The POST request creates new items, PUT updates existing ones, and DELETE removes items - all returning appropriate HTTP status codes."

---

### 5. FRONTEND DEVELOPMENT (ENHANCEMENT TASK)

#### ☐ Frontend PRD

**File to Show**: `Frontend-PRD.md`
**Lines to Highlight**:
- Lines 1-50: UI/UX requirements
- Lines 55-100: Component specifications
- Lines 105-150: API integration plans

**What to Say**:
"The Frontend PRD documents the enhanced admin panel requirements. I've specified a professional interface with search and filtering capabilities, responsive design, and comprehensive CRUD operations. The component specifications detail the interactive elements like sortable tables, real-time search, and modal forms for data editing."

#### ☐ Enhanced Frontend Admin Panel Demonstration

**Files to Show**:
1. **HTML**: `public/index.html` (Lines 1-350) - Enhanced with search/filter controls
2. **CSS**: `public/styles.css` (Lines 1-400) - Professional styling with filter panels
3. **JavaScript**: `public/script.js` (Lines 1-1200+) - Advanced functionality

**Core Features to Demonstrate**:
1. **CRUD Operations**: 
   - Add new menu items, customers, and orders
   - Edit existing data through modal forms
   - Delete data with confirmation
   - Real-time data updates

**What to Say for CRUD Operations**:
"Let me demonstrate the core CRUD functionality. I can add new menu items using this clean form interface with real-time validation. The edit functionality uses modal forms that populate with existing data. Delete operations require confirmation to prevent accidental data loss. All changes update the interface immediately without page refreshes."

2. **Search & Filter System** (NEW):
   - **Search by Name**: Type in search boxes to filter results instantly
   - **Category Filtering**: Filter menu items by category (Beverages, Food, Desserts)
   - **Status Filtering**: Filter orders by status (Pending, Completed, Cancelled)
   - **Combined Filters**: Use multiple filters simultaneously
   - **Clear Filters**: Reset all filters with one click

**What to Say for Search & Filter**:
"The enhanced search and filter system provides powerful data management capabilities. Watch as I type in the search box - results filter in real-time as I type. The category filters allow quick access to specific types of menu items. I can combine multiple filters for precise data selection, and the clear button resets everything instantly."

3. **Interactive Table Features** (NEW):
   - **Sortable Columns**: Click headers to sort by different fields
   - **Sort Indicators**: Visual arrows showing sort direction
   - **Responsive Tables**: Mobile-friendly table design

**What to Say for Interactive Tables**:
"The tables are fully interactive with sortable columns. Notice the arrow indicators that show the current sort direction. Clicking a header toggles between ascending and descending order. The responsive design ensures the interface works perfectly on all device sizes."

4. **Order Creation System** (FIXED):
   - **Customer Selection**: Choose customer from dropdown
   - **Item Selection**: Use quantity controls (+/- buttons)
   - **Real-time Order Summary**: See selected items and total instantly
   - **Individual Item Removal**: Remove items from order summary
   - **Order Total Calculation**: Accurate total calculation
   - **Clear Order**: Reset entire order with one click

**What to Say for Order Creation**:
"The order creation system demonstrates enterprise-level functionality. First, I select a customer from the dropdown. Then I can add items using the intuitive quantity controls. Watch how the order summary updates in real-time, showing selected items and calculating totals automatically. I can remove individual items or clear the entire order if needed."

#### ☐ Professional UI/UX Design

**What to Show**:
- **Modern Card-based Layout**: Clean, organized sections
- **Responsive Design**: Works on desktop, tablet, and mobile
- **Professional Color Scheme**: Consistent branding throughout
- **Interactive Elements**: Hover effects, smooth transitions
- **Toast Notifications**: Success/error messages for user feedback
- **Loading States**: Professional feedback during operations
- **Form Validation**: Real-time validation with clear error messages

**What to Say for UI/UX Design**:
"The interface features a modern, professional design with a clean card-based layout. Notice the consistent color scheme and smooth hover effects throughout. The toast notifications provide immediate feedback for user actions. Form validation happens in real-time with clear, helpful error messages. The entire interface is responsive and works seamlessly across all device sizes."

---

## 🎥 Video Recording Script

### Opening (30 seconds)
"Hello, this is my INFT4000 Assignment 1 submission for the Cafe Manager API project. I'll be demonstrating all the requirements including the PRD, source code, API documentation, and frontend interface."

**Extended Opening Script**:
"Hello, I'm presenting my INFT4000 Assignment 1 - the Cafe Manager API built using prompt engineering techniques. Today I'll walk you through my comprehensive solution including the Project Requirements Document, the complete REST API with full CRUD operations, interactive Swagger documentation, and an enhanced admin panel with advanced search and filtering capabilities. This project demonstrates enterprise-level functionality suitable for real-world cafe management."

### Section 1: PRD Demonstration (2 minutes)
"First, let me show you my Project Requirements Document..."
[Follow PRD checklist above]

**Detailed Section 1 Script**:
"Let's start with the Project Requirements Document. Here you can see I've defined comprehensive API endpoints for all three main entities - menu items, customers, and orders. Each endpoint includes detailed specifications for request and response formats. The data models show proper relationships and validation rules. I've also documented expected behaviors, error handling patterns, and business logic requirements."

### Section 2: Source Code (3 minutes)  
"Now I'll demonstrate my backend REST API with full CRUD operations..."
[Start server and show code structure]

**Detailed Section 2 Script**:
"Now let me show you the actual implementation. I'll start the server to demonstrate it's working correctly. The code follows MVC architecture with clear separation of concerns. Here are the route definitions, controller implementations, and data models. Each controller provides full CRUD functionality with proper error handling and validation. The middleware includes logging and error management."

### Section 3: Prompt Log (2 minutes)
"Here's my prompt log showing how I used AI assistance..."
[Show different prompt modes and reflect on effectiveness]

**Detailed Section 3 Script**:
"The prompt log documents my AI-assisted development process. I used three different modes - Ask mode for getting guidance, Edit mode for specific code generation, and Agent mode for complex feature implementation. You can see how my prompts evolved to become more specific and context-rich, resulting in better AI assistance."

### Section 4: API Documentation (3 minutes)
"Let me show you the Swagger documentation and test the endpoints..."
[Test all CRUD operations through Swagger UI]

**Detailed Section 4 Script**:
"Here's the interactive Swagger documentation auto-generated from my code. I can test each endpoint directly from the browser. Watch as I create a new menu item, retrieve it, update the price, and then delete it. All operations return proper HTTP status codes and JSON responses. The API also includes comprehensive error handling and validation."

### Section 5: Enhanced Frontend Demo (4 minutes)
"Finally, here's my enhanced frontend admin panel with advanced search, filtering, and order management features..."

**Demo Script**:
1. **Overview** (30 seconds): "This is a professional admin panel with comprehensive data management capabilities"

**Detailed Overview Script**:
"This is my enhanced admin panel - a professional interface designed for real-world cafe management. It provides comprehensive data management with advanced search capabilities, interactive tables, and a sophisticated order creation system."

2. **Search & Filter Features** (90 seconds):
   - "Let me demonstrate the search functionality - I can search menu items by name in real-time"
   - "Here are the category filters - I can filter by Beverages, Food, or Desserts"
   - "The system supports multiple filters simultaneously"
   - "I can sort tables by clicking column headers"

**Detailed Search & Filter Script**:
"Watch this real-time search functionality - as I type, results filter instantly without any page refresh. The category filters provide quick access to specific product types. I can combine search with category filters for precise results. The sortable columns include visual indicators showing the current sort direction. Notice how professional and responsive the interface feels."

3. **Order Creation System** (90 seconds):
   - "The order creation system allows me to select a customer"
   - "I can add items using quantity controls with real-time updates"
   - "The order summary shows selected items and calculates totals automatically"
   - "I can remove individual items or clear the entire order"

**Detailed Order Creation Script**:
"The order management system is the heart of the application. First, I select a customer from the dropdown. Then I use these quantity controls to add items - notice how the order summary updates immediately with each change. The system calculates totals in real-time, shows individual line items, and allows me to remove items or clear the entire order. This provides the functionality needed for actual cafe operations."

4. **CRUD Operations** (60 seconds):
   - "All CRUD operations work seamlessly with the enhanced interface"
   - "Toast notifications provide clear feedback"
   - "The modal forms handle validation properly"

**Detailed CRUD Operations Script**:
"Let me demonstrate the core CRUD functionality. The create forms include real-time validation with helpful error messages. Edit operations use modal forms that populate with existing data. Delete operations require confirmation to prevent accidents. Notice the toast notifications that provide immediate feedback for every action."

### Closing (30 seconds)
"This concludes my demonstration. The API provides full CRUD functionality with comprehensive search and filtering, professional UI design, and a fully functional order management system. The enhanced admin panel demonstrates enterprise-level functionality suitable for real-world cafe management."

**Extended Closing Script**:
"This concludes my comprehensive demonstration of the Cafe Manager API. I've shown you a complete solution that includes detailed project requirements, well-structured backend code, interactive API documentation, and a professional admin interface with advanced features. The system provides everything needed for real-world cafe management - from menu item management to customer tracking and order processing. The use of AI-assisted development allowed me to create enterprise-level functionality efficiently while maintaining high code quality and professional standards. Thank you for reviewing my INFT4000 Assignment 1 submission."

---

## 📝 Enhanced CRUD Testing Checklist for Admin Panel

### Menu Items CRUD with Advanced Features:
- [ ] **CREATE**: Add new menu item through admin panel form
- [ ] **READ**: View all menu items with search and filter capabilities
- [ ] **UPDATE**: Edit existing menu item through modal form
- [ ] **DELETE**: Remove menu item with confirmation dialog
- [ ] **SEARCH**: Search menu items by name in real-time
- [ ] **FILTER**: Filter by category (Beverages, Food, Desserts)
- [ ] **SORT**: Sort by name, price, category (ascending/descending)

### Customers CRUD with Enhanced Interface:
- [ ] **CREATE**: Add new customer with validation
- [ ] **READ**: View customers with search functionality
- [ ] **UPDATE**: Edit customer information seamlessly
- [ ] **DELETE**: Remove customer with proper confirmation
- [ ] **SEARCH**: Search customers by name or email
- [ ] **SORT**: Sort customers by different fields

### Orders CRUD with Complete Management:
- [ ] **CREATE**: Place new order with enhanced order builder
- [ ] **READ**: View all orders with status filtering
- [ ] **UPDATE**: Update order status and details
- [ ] **DELETE**: Cancel orders with confirmation
- [ ] **ORDER BUILDER**: Interactive item selection with quantity controls
- [ ] **REAL-TIME TOTALS**: Automatic price calculation
- [ ] **ORDER SUMMARY**: Clear display of selected items
- [ ] **FILTER BY STATUS**: Filter orders by Pending, Completed, Cancelled

### Professional UI Features to Demonstrate:
- [ ] **Responsive Design**: Show mobile/tablet compatibility
- [ ] **Interactive Tables**: Sortable columns with visual indicators
- [ ] **Search Functionality**: Real-time search across all sections
- [ ] **Filter Controls**: Professional filter panels
- [ ] **Toast Notifications**: Success/error feedback system
- [ ] **Modal Forms**: Clean, professional editing interface
- [ ] **Loading States**: Professional user feedback
- [ ] **Form Validation**: Real-time validation with error messages
- [ ] **Clear/Reset Functions**: Easy way to reset filters and forms

---

## 📁 File Reference Quick List

| Requirement | File(s) | Key Lines |
|-------------|---------|-----------|
| API PRD | `API-PRD.md` | 1-350 |
| Frontend PRD | `Frontend-PRD.md` | 1-150 |
| Prompt Log | `PROMPT_LOG.md` | 1-500 |
| Main Server | `server.js` | 1-100 |
| Routes | `src/routes/*.js` | All files |
| Controllers | `src/controllers/*.js` | All files |
| Models | `src/models/*.js` | All files |
| Frontend Enhanced | `public/*.html,css,js` | All files (1200+ lines JS) |
| README | `README.md` | 1-200 |
| Deployment | `RENDER_DEPLOYMENT.md` | 1-100 |

## 🚀 Pre-Recording Setup

1. **Clear Terminal**: Start with clean terminal
2. **Start Server**: Have server running on port 3000
3. **Open Browser**: Have Swagger UI ready at `http://localhost:3000/api-docs`
4. **Prepare Files**: Have all files open in VS Code
5. **Test Database**: Ensure SQLite database has sample data
6. **Check Network**: Verify deployed API is accessible

**Total Video Length**: Approximately 13-16 minutes
**Recommended Recording**: Use screen recording with clear audio narration focusing on the enhanced admin panel features
