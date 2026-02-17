# Project: Hubleto AI-generated ERP

## Architectural Guidelines
- **Approach:**
  - A Hubleto-based customized ERP solutions
- **Core Principle:**
  - Core backend framework is Hubleto framework (https://github.com/hubleto/framework)
  - Core fronted framework is Hubleto React UI (https://github.com/hubleto/react-ui)
  - Learn architectural documentation from https://developer.hubleto.com
  - Learn existing functionality in community Hubleto apps (https://github.com/hubleto/erp/apps)
  - Each new functionality must be encapsulated as a custom Hubleto app (namespace Hubleto\App\Custom)
  - Each app uses a Model-View-Controller (MVC) architecture
- **File structure:**
  - Custom apps (namespace Hubleto\App\Custom) stored only in src/apps
  - Each app must follow files and folder structure described in https://developer.hubleto.com/v0/docs/erp/apps/folder-structure
- **Data Access:**
  - All data access must go through a repository interface. Never use ORM models directly in Use Cases.
  - Use Eloquent Record Manager for data access
  - Each model must have its appropriate record manager
  - Each model must have UPPERCASE relations for each Lookup column.
  - Each relation must be implemented in record manager, either as eloquent's BelongsTo or HasMany
- **Anti-Patterns:**
  - No direct API calls in component rendering logic.

## Directory structure

- `PROJECT_FOLDER/`: Folder created by running `composer create-project hubleto/erp-project .`
  - `src/`: Core application logic
    - `src/apps/`: Custom apps for this project
      - `src/apps/MyCustomApp/Components/`: Hubleto React UI components for tables and forms (e.g. FormContact.tsx and TableContacts.tsx)
      - `src/apps/MyCustomApp/Models/`: Models used in the app.
      - `src/apps/MyCustomApp/Models/RecordManagers/`: Record managers for each model
      - `src/apps/MyCustomApp/Controllers/`: PHP controllers used in the app (extending from Hubleto\Erp\Controller).
      - `src/apps/MyCustomApp/Views/`: Views used in the app (Twig)
  - `tests/`: PHPUnit-compatible tests

## Technical Constraints
- **Backend language:** PHP
- **Frontend language:** HTML with Twig, React
- **Backend framework:** PHP (Hubleto framework, https://github.com/hubleto/framework)
- **Frontend framework:** Hubleto React UI framework (https://github.com/hubleto/react-ui)
- **Database:** SQL (accesesed via Record Managers)

## Commands
- **Create initial project files and folder structure:** `composer create-project hubleto/erp-project .`

## Description of the app
// PUT HERE DESCRIPTION OF THE APP YOU WANT TO GENERATE
