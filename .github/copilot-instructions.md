# AI Rules for HealthyMealAI

## CODING_PRACTICES

### Guidelines for SUPPORT_LEVEL

#### SUPPORT_EXPERT

- Favor elegant, maintainable solutions over verbose code. Assume understanding of language idioms and design patterns.
- Highlight potential performance implications and optimization opportunities in suggested code.
- Frame solutions within broader architectural contexts and suggest design alternatives when appropriate.
- Focus comments on 'why' not 'what' - assume code readability through well-named functions and variables.
- Proactively address edge cases, race conditions, and security considerations without being prompted.
- When debugging, provide targeted diagnostic approaches rather than shotgun solutions.
- Suggest comprehensive testing strategies rather than just example tests, including considerations for mocking, test organization, and coverage.

### Guidelines for DOCUMENTATION

#### SWAGGER

- Define comprehensive schemas for all request and response objects
- Use semantic versioning in API paths to maintain backward compatibility
- Implement detailed descriptions for endpoints, parameters, and {{domain_specific_concepts}}
- Configure security schemes to document authentication and authorization requirements
- Use tags to group related endpoints by resource or functional area
- Implement examples for all endpoints to facilitate easier integration by consumers


### Guidelines for VERSION_CONTROL

#### GITHUB

- Use pull request templates to standardize information provided for code reviews
- Implement branch protection rules for {{protected_branches}} to enforce quality checks
- Configure required status checks to prevent merging code that fails tests or linting
- Use GitHub Actions for CI/CD workflows to automate testing and deployment
- Implement CODEOWNERS files to automatically assign reviewers based on code paths
- Use GitHub Projects for tracking work items and connecting them to code changes

#### GIT

- Use conventional commits to create meaningful commit messages
- Use feature branches with descriptive names following {{branch_naming_convention}}
- Write meaningful commit messages that explain why changes were made, not just what
- Keep commits focused on single logical changes to facilitate code review and bisection
- Use interactive rebase to clean up history before merging feature branches
- Leverage git hooks to enforce code quality checks before commits and pushes

#### CONVENTIONAL_COMMITS

- Follow the format: type(scope): description for all commit messages
- Use consistent types (feat, fix, docs, style, refactor, test, chore) across the project
- Define clear scopes based on {{project_modules}} to indicate affected areas
- Include issue references in commit messages to link changes to requirements
- Use breaking change footer (!: or BREAKING CHANGE:) to clearly mark incompatible changes
- Configure commitlint to automatically enforce conventional commit format

### Guidelines for ARCHITECTURE

#### CLEAN_ARCHITECTURE

- Follow CleanCode principles to ensure code is easy to read, understand, and maintain
- Strictly separate code into layers: entities, use cases, interfaces, and frameworks
- Ensure dependencies point inward, with inner layers having no knowledge of outer layers
- Implement domain entities that encapsulate {{business_rules}} without framework dependencies
- Use interfaces (ports) and implementations (adapters) to isolate external dependencies
- Create use cases that orchestrate entity interactions for specific business operations
- Implement mappers to transform data between layers to maintain separation of concerns

#### DDD

- Define bounded contexts to separate different parts of the domain with clear boundaries
- Implement ubiquitous language within each context to align code with business terminology
- Create rich domain models with behavior, not just data structures, for {{core_domain_entities}}
- Use value objects for concepts with no identity but defined by their attributes
- Implement domain events to communicate between bounded contexts
- Use aggregates to enforce consistency boundaries and transactional integrity

### Guidelines for STATIC_ANALYSIS

#### PRETTIER

- Define a consistent .prettierrc configuration across all {{project_repositories}}
- Configure editor integration to format on save for immediate feedback
- Use .prettierignore to exclude generated files, build artifacts, and {{specific_excluded_patterns}}
- Set printWidth based on team preferences (80-120 characters) to improve code readability
- Configure consistent quote style and semicolon usage to match team conventions
- Implement CI checks to ensure all committed code adheres to the defined style

#### ESLINT

- Configure project-specific rules in eslint.config.js to enforce consistent coding standards
- Use shareable configs like eslint-config-airbnb or eslint-config-standard as a foundation
- Implement custom rules for {{project_specific_patterns}} to maintain codebase consistency
- Configure integration with Prettier to avoid rule conflicts for code formatting
- Use the --fix flag in CI/CD pipelines to automatically correct fixable issues
- Implement staged linting with husky and lint-staged to prevent committing non-compliant code

## BACKEND

### Guidelines for DOTNET

  .NET Development Rules

  You are a senior .NET backend developer and an expert in C#, ASP.NET Core, and Entity Framework Core.

  Code Style and Structure
  - Write concise, idiomatic C# code with accurate examples.
  - Follow .NET and ASP.NET Core conventions and best practices.
  - Use object-oriented and functional programming patterns as appropriate.
  - Prefer LINQ and lambda expressions for collection operations.
  - Use descriptive variable and method names (e.g., 'IsUserSignedIn', 'CalculateTotal').
  - Structure files according to .NET conventions (Controllers, Models, Services, etc.).

  Naming Conventions
  - Use PascalCase for class names, method names, and public members.
  - Use camelCase for local variables and private fields.
  - Use UPPERCASE for constants.
  - Prefix interface names with "I" (e.g., 'IUserService').

  #C# and .NET Usage
  - Use C# 10+ features when appropriate (e.g., record types, pattern matching, null-coalescing assignment).
  - Leverage built-in ASP.NET Core features and middleware.
  - Use Entity Framework Core effectively for database operations.

  Syntax and Formatting
  - Follow the C# Coding Conventions (https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
  - Use C#'s expressive syntax (e.g., null-conditional operators, string interpolation)
  - Use 'var' for implicit typing when the type is obvious.

  Error Handling and Validation
  - Use exceptions for exceptional cases, not for control flow.
  - Implement proper error logging using built-in .NET logging or a third-party logger.
  - Use Data Annotations or Fluent Validation for model validation.
  - Implement global exception handling middleware.
  - Return appropriate HTTP status codes and consistent error responses.

  API Design
  - Follow RESTful API design principles.
  - Use attribute routing in controllers.
  - Implement versioning for your API.
  - Use action filters for cross-cutting concerns.

  Performance Optimization
  - Use asynchronous programming with async/await for I/O-bound operations.
  - Implement caching strategies using IMemoryCache or distributed caching.
  - Use efficient LINQ queries and avoid N+1 query problems.
  - Implement pagination for large data sets.
  - Use compiled queries for frequently executed queries.
  - Prefer async eliding for I/O-bound operations.
  

  Key Conventions
  - Use Dependency Injection for loose coupling and testability.
  - Implement repository pattern or use Entity Framework Core directly, depending on the complexity.
  - Write mapping extension methods for object-to-object mapping if needed.
  - Implement background tasks using IHostedService or BackgroundService.

  Testing
  - Write unit tests using xUnit.
  - Use Moq for mocking dependencies.
  - Implement integration tests for API endpoints.

  Security
  - Use Authentication and Authorization middleware.
  - Implement JWT authentication for stateless API authentication.
  - Use HTTPS and enforce SSL.
  - Implement proper CORS policies.

  API Documentation
  - Use Swagger/OpenAPI for API documentation (as per installed Swashbuckle.AspNetCore package).
  - Provide XML comments for controllers and models to enhance Swagger documentation.

  Follow the official Microsoft documentation and ASP.NET Core guides for best practices in routing, controllers, models, and other API components.


#### ENTITY_FRAMEWORK

- Use the repository and unit of work patterns to abstract data access logic and simplify testing
- Implement eager loading with Include() to avoid N+1 query problems for {{entity_relationships}}
- Use migrations for database schema changes and version control with proper naming conventions
- Apply appropriate tracking behavior (AsNoTracking() for read-only queries) to optimize performance
- Implement query optimization techniques like compiled queries for frequently executed database operations
- Use value conversions for complex property transformations and proper handling of {{custom_data_types}}

#### ASP_NET

- Use minimal APIs for simple endpoints in .NET 6+ applications to reduce boilerplate code
- Implement the mediator pattern with MediatR for decoupling request handling and simplifying cross-cutting concerns
- Use API controllers with model binding and validation attributes for {{complex_data_models}}
- Apply proper response caching with cache profiles and ETags for improved performance on {{high_traffic_endpoints}}
- Implement proper exception handling with ExceptionFilter or middleware to provide consistent error responses
- Use dependency injection with scoped lifetime for request-specific services and singleton for stateless services


## DATABASE

### Guidelines for SQL

#### POSTGRES

- Use connection pooling to manage database connections efficiently
- Implement JSONB columns for semi-structured data instead of creating many tables for {{flexible_data}}
- Use materialized views for complex, frequently accessed read-only data


## DEVOPS

### Guidelines for CI_CD

#### GITHUB_ACTIONS

- Check if `package.json` exists in project root and summarize key scripts
- Check if `.nvmrc` exists in project root
- Check if `.env.example` exists in project root to identify key `env:` variables
- Always use terminal command: `git branch -a | cat` to verify whether we use `main` or `master` branch
- Always use `env:` variables and secrets attached to jobs instead of global workflows
- Always use `npm ci` for Node-based dependency setup
- Extract common steps into composite actions in separate files
- Once you're done, as a final step conduct the following: for each public action always use <tool>"Run Terminal"</tool> to see what is the most up-to-date version (use only major version) - extract tag_name from the response:
- ```bash curl -s https://api.github.com/repos/{owner}/{repo}/releases/latest ```


### Guidelines for CONTAINERIZATION

#### DOCKER

- Use multi-stage builds to create smaller production images
- Implement layer caching strategies to speed up builds for {{dependency_types}}
- Use non-root users in containers for better security


### Guidelines for CLOUD

#### AZURE

- Use Azure Resource Manager (ARM) templates or Bicep for infrastructure as code
- Implement Azure AD for authentication and authorization of {{user_types}}
- Use managed identities instead of service principals when possible


## TESTING

### Guidelines for E2E

#### PLAYWRIGHT

- Initialize configuration only with Chromium/Desktop Chrome browser
- Use browser contexts for isolating test environments
- Implement the Page Object Model for maintainable tests
- Use locators for resilient element selection
- Leverage API testing for backend validation
- Implement visual comparison with expect(page).toHaveScreenshot()
- Use the codegen tool for test recording
- Leverage trace viewer for debugging test failures
- Implement test hooks for setup and teardown
- Use expect assertions with specific matchers
- Leverage parallel execution for faster test runs


## FRONTEND

### Guidelines for ANGULAR

#### ANGULAR_CODING_STANDARDS

- Use standalone components, directives, and pipes instead of NgModules
- Implement signals for state management instead of traditional RxJS-based approaches
- Use the new inject function instead of constructor injection
- Implement control flow with @if, @for, and @switch instead of *ngIf, *ngFor, etc.
- Leverage functional guards and resolvers instead of class-based ones
- Use the new deferrable views for improved loading states
- Implement OnPush change detection strategy for improved performance
- Use TypeScript decorators with explicit visibility modifiers (public, private)
- Leverage Angular CLI for schematics and code generation
- Implement proper lazy loading with loadComponent and loadChildren
