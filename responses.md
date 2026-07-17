# Prompt and Response Log

This file records the prompts supplied for the eShopOnWeb testing work and the corresponding responses generated for the repository.

## 1. Generate a Copilot instructions file

### Prompt
You are assisting in a .NET 10 e-commerce testing project (eShopOnWeb).

Generate a .github/copilot-instructions.md file.

Requirements:
- Follow xUnit testing conventions.
- Use Arrange-Act-Assert (AAA) pattern.
- Use meaningful and descriptive test names.
- Keep tests independent and repeatable.
- Reuse existing project fixtures and helpers whenever possible.
- Use Playwright with role-based and accessible locators.
- Avoid XPath unless there is no suitable alternative.
- Do not modify production code while generating tests.
- Review every AI-generated test before committing.
- Ensure generated code follows existing project coding standards.

### Response
Created [.github/copilot-instructions.md](.github/copilot-instructions.md) with repository-specific guidance for xUnit, AAA structure, descriptive test naming, fixture reuse, accessible Playwright patterns, and review expectations.

## 2. Generate setup notes

### Prompt
Generate setup-notes.md for the eShopOnWeb project.

Include:
- .NET SDK version
- Repository clone steps
- Restore command
- Build command
- Test command
- Application run command
- Problems encountered during setup
- Solutions applied

Write professionally in Markdown.

### Response
Created [docs/testing/setup-notes.md](docs/testing/setup-notes.md) with setup steps for .NET 10, clone and restore instructions, build and test commands, local app run guidance, and a short section covering setup issues and fixes.

## 3. Create a testing strategy document

### Prompt
Create a testing strategy document for an ASP.NET Core e-commerce application.

Include:
- Testing objectives
- Scope
- Unit testing
- Integration testing
- End-to-End testing with Playwright
- Risk areas
- GitHub Copilot usage guidelines
- Exit criteria

Return Markdown only.

### Response
Created [docs/testing/test-strategy.md](docs/testing/test-strategy.md) covering testing objectives, scope, unit/integration/e2e guidance, high-risk areas, Copilot usage guidance, and release exit criteria.

## 4. Generate xUnit unit tests

### Prompt
Generate xUnit unit tests for this class.

Requirements:
- Follow Arrange Act Assert pattern.
- Cover positive and negative scenarios.
- Use descriptive test names.
- Reuse existing project helpers.
- Do not modify production code.
- Explain assumptions with comments only where necessary.

### Response
Added unit tests for basket behavior in:
- [tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketAddItem.cs](tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketAddItem.cs)
- [tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketRemoveEmptyItems.cs](tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketRemoveEmptyItems.cs)
- [tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketTests.cs](tests/UnitTests/ApplicationCore/Entities/BasketTests/BasketTests.cs)
- [tests/UnitTests/ApplicationCore/Services/BasketServiceTests/BasketServiceTests.cs](tests/UnitTests/ApplicationCore/Services/BasketServiceTests/BasketServiceTests.cs)

These tests cover positive and negative basket scenarios with descriptive names and no production-code changes.

## 5. Generate an integration test

### Prompt
Generate an integration test following the existing IntegrationTests project conventions.

Scenario:
Verify the catalog or home page loads successfully.

Requirements:
- Reuse project fixtures.
- Do not duplicate setup code.
- Use xUnit.
- Return production-ready code.

### Response
Added an integration-style functional test at [tests/FunctionalTests/Web/Pages/CatalogPageOnGet.cs](tests/FunctionalTests/Web/Pages/CatalogPageOnGet.cs) using the existing web test fixture and repository conventions to verify that the catalog/home page loads successfully.

## 6. Add supporting testing documentation

### Prompt
Generate supporting documentation for testing setup, test data, defect analysis, and review guidance.

### Response
Added supporting documents in [docs/testing](docs/testing):
- [docs/testing/test-data.md](docs/testing/test-data.md)
- [docs/testing/defect-analysis.md](docs/testing/defect-analysis.md)
- [docs/testing/copilot-review-checklist.md](docs/testing/copilot-review-checklist.md)
- [README-AI-TESTING-SUBMISSION.md](README-AI-TESTING-SUBMISSION.md)

## 7. Add browser automation coverage

### Prompt
Generate Playwright end-to-end tests for catalog and basket flows.

### Response
Added Playwright browser scenarios in [tests/e2e/catalog.spec.ts](tests/e2e/catalog.spec.ts) and [tests/e2e/basket.spec.ts](tests/e2e/basket.spec.ts), along with Playwright configuration in [playwright.config.ts](playwright.config.ts) and CI wiring in [.github/workflows/playwright.yml](.github/workflows/playwright.yml).
