# Commerce: Online Auction Platform

This project is part of CS50’s Web Programming with Python and JavaScript course. it is an implementation of an auction site using Django. The project includes an app called `auctions` that enables users to create, bid, and comment on auction listings. Below is a comprehensive guide to the functionality and specifications of this application.

## Project Structure

### URL Configuration
- The URL configuration is defined in `auctions/urls.py`.
- Predefined routes:
  - `/` (index): Displays active auction listings.
  - `/login`: Renders a login form; authenticates and logs in users upon form submission.
  - `/logout`: Logs users out and redirects to the index page.
  - `/register`: Allows users to register an account.

### Views
- Defined in `auctions/views.py`:
  - `index`: Displays active listings (initially renders an empty template).
  - `login_view`: Handles login via a form (GET and POST methods).
  - `logout_view`: Logs out the user and redirects to the index page.
  - `register`: Allows new users to register and creates their accounts.

### Templates
- Layout and dynamic rendering handled in `auctions/templates/auctions/layout.html`.
- Content is conditionally displayed using `user.is_authenticated` to check login status.

### Models
- Defined in `auctions/models.py`:
  - Includes a `User` model inheriting from `AbstractUser`.
  - Additional models will represent auction listings, bids, comments, and categories.

---

## Running the Application
1. Start the Django development server:
   ```bash
   python manage.py runserver
   ```
2. Open the application in your browser.
3. Register a new account, log in, and explore the features.

---

## Specification
The following features are implemented in the project:

### Models
- **User Model**:
  - Inherits from `AbstractUser`.
  - Extendable for additional user fields.
- **Auction Listings**:
  - Fields: title, description, starting bid, optional image URL, category, etc.
- **Bids**:
  - Tracks user bids on listings.
- **Comments**:
  - Enables user comments on listings.
- Additional models as required for functionality.

### Core Features
1. **Create Listing**:
   - Users can create new auction listings with a title, description, starting bid, optional image URL, and category.

2. **Active Listings Page**:
   - Default route displays all active listings with title, description, current price, and image (if available).

3. **Listing Page**:
   - Displays detailed information about a specific listing.
   - Signed-in users can:
     - Add/remove the listing to/from their Watchlist.
     - Place a bid (must meet criteria).
     - Close the auction if they created the listing.
   - Displays all comments on the listing.
   - Declares a winner if the auction is closed.

4. **Watchlist**:
   - Signed-in users can view and manage their Watchlist.

5. **Categories**:
   - Displays all listing categories.
   - Clicking a category shows all active listings in that category.

6. **Django Admin Interface**:
   - Admins can view, add, edit, and delete listings, comments, and bids.




