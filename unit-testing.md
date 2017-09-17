# Unit testing

## Patterns
- Arrange, Act, Assert
  - Arrange: Arrange everything you need for the unit test (Ideally you want it to be clearly readable, do not create methods since it affects readability unless it is repeated in mostly every test case)
  - Act: Do the action in which you are testing, i.e. call the method
  - Assert: assert that it does what it is meant to.
- Unit testing should be Atomic & Fast
- Tests for the Parent or Wrapper classes/viewmodels should not call down the stack. Instead, they should be isolated to only test that level.
- When doing TDD - you can set everything up in it's own file to make it isolated and atomic. When it is working as correct you can then move it into the structure.
  - Write failing test cases, Write code to try and make it pass, Refactor.

## Shims (Indicates code smell)
- If you need to use Shims, then that is a Code smell indicating the structure of the code could be wrong 
- Shims are used for typically legacy code where it is difficult to change and difficult to test 
  - An example usecase for shims would be a controller method that generates a new class in it. In this case, you can't really mock it unless you mock the whole method which defeats the purpose
- If you expect a Shim class method to be called, you will have to do a manual boolean check to test it is called
- To Shim a library, right click on the library, select "Add to Fakes", this will generate all the classes and everything inside that library for you.

## Mocks (Ideal)
- Mocks give you more control
- Using Moq library: Can do callback() etc


