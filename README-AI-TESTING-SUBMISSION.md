# AI Testing Submission

## Project overview
This submission documents the testing work completed for the eShopOnWeb project, an ASP.NET Core e-commerce reference application. The focus was on creating and reviewing test assets that align with the repository’s existing xUnit, functional, and Playwright testing patterns while avoiding production code changes.

## Repository setup
The repository was prepared using the existing .NET 10-based solution structure. The required SDK version is .NET 10.0.0, and the local environment used .NET SDK 10.0.203. The project was opened from the repository root and tested using the existing solution and test projects under the repository’s tests folder.

## Testing approach
The testing approach followed the repository’s established conventions:

- xUnit for unit and functional-style tests
- Arrange-Act-Assert structure for new tests
- Descriptive and meaningful test names
- Reuse of existing fixtures, helpers, and page-object patterns where available
- Playwright for end-to-end browser scenarios with accessible, role-based locators
- Avoidance of XPath and unnecessary hard-coded waits

## GitHub Copilot prompts used
The following types of prompts were used to generate and refine test artifacts:

- Generate xUnit unit tests for a basket-related domain class
- Generate an integration-style functional test for the catalog/home page
- Generate a Playwright end-to-end test for adding a product to the basket
- Generate supporting documentation for testing setup, test data, defect analysis, and review checklists

## Manual changes after AI generation
After AI-generated content was produced, the following manual refinements were applied:

- Verified that generated tests matched the repository’s existing namespace and file organization patterns
- Adjusted test names and assertions to be more descriptive and consistent with the project style
- Ensured no production code was modified
- Confirmed that Playwright tests used accessible selectors and reasonable assertions
- Reviewed generated documentation for clarity and professionalism

## Tests executed
The following verification commands were used:

```bash
dotnet test tests/UnitTests/UnitTests.csproj --filter BasketTests
dotnet test tests/FunctionalTests/FunctionalTests.csproj --filter CatalogPageOnGet
dotnet test tests/EndToEndTests/EndToEndTests.csproj --filter BasketTests --no-restore
```

## Known limitations
- The environment encountered an xUnit process-launch issue during some test executions in the shell, which prevented full runtime execution of the functional and end-to-end test hosts from completing in this session.
- Some package warnings were emitted during restore and build, including known dependency advisories and pruning warnings, but these did not block the creation of the requested test assets.
- Playwright scenarios depend on the web application being available and correctly started by the existing browser fixture.

## Conclusion
The requested AI-assisted testing artifacts were created and aligned with the project’s existing conventions. The work includes unit-test guidance, functional and Playwright testing examples, supporting documentation, and review materials that can be used to strengthen the quality and maintainability of the eShopOnWeb test suite.
