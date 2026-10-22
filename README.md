# Laravel Task Manager Application

A modern, readable, and robust Task Management Web Application built with **Laravel 13** and **PHP 8.3**. Designed and implemented following clean Laravel conventions, this application provides full task lifecycle management, dynamic drag-and-drop task reordering, project filtering, and custom input validation.

---

## Requirements & Features Compliance

* **Task Management (CRUD):** Create, edit, update, and delete tasks seamlessly with persistent storage in MySQL.
* **Drag-and-Drop Reordering:** Drag tasks in the browser using the local [`sortable.min.js`](https://cdn.jsdelivr.net/npm/sortablejs@1.15.6/Sortable.min.js) library (see also [SortableJS Live Demos](https://sortablejs.github.io/Sortable/)) to adjust priorities in real-time (#1 priority at the top, #2 next down, etc.) via asynchronous AJAX updates.
* **Smart Drag Guarding:** Built-in checks prevent unnecessary network requests and database updates if a task is clicked or dropped without a position change.
* **Bonus Feature — Project Functionality:** Filter tasks dynamically by selecting a project from the dropdown list. The interface highlights matching project tasks while maintaining real-time updates.
* **Input Validation:** Enforces clean input rules, requiring at least 6 alphabetic characters for task names (ignoring spaces and special characters).
* **Self-Contained Asset Delivery:** Bundled with local JS assets for offline support, coupled with Laravel Vite for development and production build workflows.

---

## Environment & Tech Stack

This project strictly meets and exceeds the system requirements:

* **Framework:** Laravel `13.37.0` (Min. v11 requirement met)
* **Language:** PHP `8.3.35` (Min. v8.3 requirement met)
* **Package Manager:** Composer `2.9.2`
* **Database:** MySQL
* **Frontend:** Blade Templating, Vanilla JavaScript (ES6+), SortableJS, Vite
* **Asset Bundling:** Vite / Local JavaScript Hosting

---

### Project Architecture

* **`app/Http/Controllers/`** - Contains the task and project controllers handling CRUD logic and status updates.
* **`database/migrations/ & seeders/`** - Schema definitions and initial mock data seeders.
* **`resources/js/app.js`** - Frontend logic integrating SortableJS for drag-and-drop reordering.
* **`resources/views/tasks/`** - Blade templates including the main interactive dashboard (`index.blade.php`) and task forms.
* **`routes/web.php`** - Web routes and AJAX endpoints for asynchronous task updates.

---

## Step-by-Step Setup

1. **Option A: Clone & Navigate to the Repository  [OR]  Option B: Extract ZIP Archive**

   ```
   Choose **Option A** if you are pulling from GitHub

   git clone https://github.com/ErnestKekeke/coalition_technologies_task_manager.git
   cd coalition_technologies_task_manager

   Open the extracted folder in your terminal or code editor (e.g., VS Code).
   ..............
   ..............

   Choose **Option B** Extract ZIP Archive

   Extract the downloaded project ZIP archive.
   Open the extracted folder in your terminal or code editor (e.g., VS Code).
   
   ```

2. **Install PHP Dependencies**

   ```
   composer install
   
   ```

3. **Install Frontend Dependencies**

   ```
   npm install
   
   ```

4. **Environment Configuration**
   Duplicate `.env.example` to create your `.env` configuration file:

   ```
   cp .env.example .env
   
   ```

   Generate a new application encryption key:

   ```
   php artisan key:generate
   
   ```

5. **Database Configuration**
   Ensure your local MySQL server is running and create a database named `task_manager`:

   ```
   CREATE DATABASE task_manager;
   
   ```

   Then configure your `.env` settings accordingly:

   ```
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=task_manager
   DB_USERNAME=root
   DB_PASSWORD=
   
   ```

6. **Run Database Migrations & Seeders**
   Execute database migrations to set up the necessary tables and seed initial project/task data:

   ```
   php artisan migrate --seed
   
   ```

   *If you need to wipe and re-run migrations with seeds:*

   ```
   php artisan migrate:fresh --seed
   
   ```

7. **Compile Frontend Assets**

   * **Development Mode (with Hot Module Replacement):**

     ```
     npm run dev
     
     ```

   * **Production Build:**

     ```
     npm run build
     
     ```

8. **Serve the Application**
   Launch Laravel's development server:

   ```
   php artisan serve
   
   ```

   Open your browser and navigate to `http://127.0.0.1:8000`.

## Testing & Verification

1. **Filtering Tasks:** Use the project dropdown selector on the main tasks view to view tasks tied to specific projects.

2. **Reordering Tasks:** Drag and drop tasks up or down within a project list. Priority numbers will immediately update in the UI and persist in the database via AJAX.

3. **Task CRUD:** Add a new task, edit its properties, and verify changes persist after saving.

---

## License

This project is open-sourced under the [MIT License](LICENSE).

---

## Author

**Ernest Kekeke**  
*Senior Full-Stack Developer / DevOps Engineer*