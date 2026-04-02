# Project Overrides — Codebase Exploration

## Project Structure
<!-- Key directories and their roles. Saves search time by providing a map. -->
- <!-- e.g., src/api/ — REST endpoint handlers -->
- <!-- e.g., src/services/ — business logic layer -->
- <!-- e.g., src/models/ — database models and schemas -->
- <!-- e.g., packages/ — monorepo workspace packages -->

## Entry Points
<!-- Where to start exploring for common question types. -->
- App bootstrap: <!-- e.g., src/main.ts -->
- Route definitions: <!-- e.g., src/routes/index.ts -->
- Config loading: <!-- e.g., src/config.ts -->

## Naming Conventions
<!-- Helps the agent try the right patterns first. -->
- Files: <!-- e.g., kebab-case (user-service.ts) -->
- Classes: <!-- e.g., PascalCase (UserService) -->
- Tests: <!-- e.g., *.test.ts co-located with source -->
- DB migrations: <!-- e.g., YYYYMMDD_description.sql in migrations/ -->

## Ignore Patterns
<!-- Directories/files to skip during exploration — reduces noise. -->
- <!-- e.g., node_modules/, dist/, .next/, coverage/ -->
- <!-- e.g., src/generated/ — auto-generated, not useful for understanding logic -->
- <!-- e.g., vendor/ — third-party code, not project code -->

## MCP Tools Available
<!-- List any MCP search tools installed in this project's environment. -->
- <!-- e.g., search_code via claude-context MCP server -->
- <!-- e.g., None — use Grep with synonyms for semantic queries -->
