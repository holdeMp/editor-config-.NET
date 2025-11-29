# EditorConfig Documentation

## Overview

This repository contains a comprehensive `.editorconfig` file that enforces consistent coding standards across the entire SteamTrade project. The configuration ensures uniform code formatting, naming conventions, and coding practices regardless of the development environment or IDE being used.

## What is EditorConfig?

EditorConfig is a file format and collection of text editor plugins that helps maintain consistent coding styles between different editors and IDEs. It defines coding style rules that are automatically applied when editing files, ensuring consistency across team members and different development environments.

## File Structure

The `.editorconfig` file is organized into several logical sections:

### 1. Global Settings

-   **Root**: `true` - This is the top-most EditorConfig file
-   **Default encoding**: UTF-8
-   **Default indentation**: 4 spaces
-   **Line endings**: Platform-specific (CRLF for Windows, LF for Unix)
-   **File endings**: Always insert final newline
-   **Whitespace**: Trim trailing whitespace

### 2. File Type Specific Settings

Different file types have specific formatting rules:

#### Visual Studio Files

-   **Solution files** (`.sln`): Tab indentation
-   **Project files** (`.csproj`, `.vbproj`, etc.): 2-space indentation

#### Configuration Files

-   **XML/Config files**: 2-space indentation
-   **JSON files**: 2-space indentation
-   **YAML files**: 2-space indentation

#### Web Development Files

-   **HTML/CSS/JavaScript/TypeScript**: 2-space indentation
-   **Markdown**: Preserve trailing whitespace (for line breaks)

#### Script Files

-   **Batch files** (`.cmd`, `.bat`): CRLF line endings
-   **Shell scripts** (`.sh`): LF line endings
-   **Makefiles**: Tab indentation

### 3. .NET Code Style Rules

#### General .NET Rules

-   **Analyzer severity**: Warning level for all .NET Code Style rules
-   **Qualification**: Avoid unnecessary `this.` qualifiers
-   **Framework types**: Prefer language keywords over framework type names
-   **Accessibility**: Require accessibility modifiers for non-interface members
-   **Readonly fields**: Prefer readonly fields when possible

#### Modifier Order

-   **C#**: `public, private, protected, internal, static, extern, new, virtual, abstract, sealed, override, readonly, unsafe, volatile, async`
-   **VB.NET**: `Partial, Default, Private, Protected, Public, Friend, NotOverridable, Overridable, MustOverride, Overloads, Overrides, MustInherit, NotInheritable, Static, Shared, Shadows, ReadOnly, WriteOnly, Dim, Const, WithEvents, Widening, Narrowing, Custom, Async`

#### Expression Preferences

-   **Object initializers**: Prefer object initializers
-   **Collection initializers**: Prefer collection initializers
-   **Tuple names**: Prefer explicit tuple names
-   **Auto properties**: Prefer auto-implemented properties
-   **Compound assignment**: Prefer compound assignment operators
-   **String interpolation**: Prefer simplified interpolation
-   **Boolean expressions**: Prefer simplified boolean expressions

#### Null Checking

-   **Coalesce expressions**: Prefer null coalescing operator (`??`)
-   **Null propagation**: Prefer null conditional operator (`?.`)
-   **Null checks**: Prefer `is null` over reference equality methods

### 4. C# Specific Style Rules

#### Var Usage

-   **Built-in types**: Don't use `var` for built-in types
-   **Apparent types**: Use `var` when type is apparent from context
-   **Elsewhere**: Don't use `var` in other cases

#### Expression-Bodied Members

-   **Methods, constructors, operators, properties, indexers, accessors, lambdas, local functions**: Prefer expression-bodied syntax when appropriate

#### Pattern Matching

-   **Pattern matching over casting**: Prefer pattern matching over `is` with cast
-   **Pattern matching over null checks**: Prefer pattern matching over `as` with null check
-   **Switch expressions**: Prefer switch expressions over switch statements
-   **Pattern matching**: Prefer pattern matching in general
-   **Not patterns**: Prefer `is not` patterns

#### Modern C# Features

-   **Inlined variable declarations**: Prefer inlined variable declarations
-   **Default expressions**: Prefer simple default expressions
-   **Pattern locals**: Prefer pattern locals over anonymous functions
-   **Deconstructed variables**: Prefer deconstructed variable declarations
-   **Index and range operators**: Prefer index and range operators
-   **Implicit object creation**: Prefer implicit object creation when type is apparent

#### Code Block Preferences

-   **Braces**: Prefer braces for all control structures
-   **Using statements**: Prefer simple using statements
-   **Using directive placement**: Place using directives inside namespace

### 5. Naming Conventions

#### Naming Styles

-   **camelCase**: For local variables, parameters, and private fields
-   **PascalCase**: For public members, types, and constants
-   **Interface prefix**: Interfaces must start with uppercase 'I'
-   **Type parameter prefix**: Generic type parameters must start with uppercase 'T'
-   **Private field prefix**: Private fields must start with underscore '\_'
-   **Async suffix**: Async methods must end with 'Async'

#### Field Naming Rules

-   **Public/Protected constants**: Must be PascalCase
-   **Public/Protected static readonly**: Must be PascalCase
-   **Other public/protected fields**: Not allowed (enforced by StyleCop)
-   **Private fields**: Must be underscore_camelCase
-   **Local variables**: Must be camelCase

#### General Naming Rules

-   **PascalCase required for**: Namespaces, classes, enums, structs, delegates, events, methods, properties
-   **Interface naming**: PascalCase with 'I' prefix
-   **Generic parameters**: PascalCase with 'T' prefix
-   **Parameters**: camelCase
-   **Async methods**: Must have 'Async' suffix

### 6. Diagnostic Severity Overrides

The configuration includes specific severity levels for various code analysis rules:

#### Performance Rules (Error level)

-   **CA1802**: Use literals where appropriate
-   **CA1805**: Don't initialize unnecessarily
-   **CA1812**: Avoid uninstantiated internal classes
-   **CA1820**: Test empty strings using length
-   **CA1866**: Use char overload instead of string overload
-   **CA1865**: Use char overload for StartsWith/EndsWith

#### Reliability Rules (Error level)

-   **CA2000**: Dispose objects before losing scope
-   **CA2002**: Don't lock on objects with weak identity
-   **CA2009**: Don't call ToImmutableCollection on ImmutableCollection values
-   **CA2011**: Don't assign property within its setter
-   **CA2013**: Don't use ReferenceEquals with value types

#### Async Rules (Error level)

-   **CS4014**: Call not awaited
-   **CS4017**: Async methods should return Task instead of void
-   **CA1849**: Call async methods when in async context

## Benefits

1. **Consistency**: Ensures all team members write code in the same style
2. **Automation**: Automatically formats code according to project standards
3. **IDE Independence**: Works across different editors and IDEs
4. **Code Quality**: Enforces best practices and coding standards
5. **Team Productivity**: Reduces code review time spent on formatting issues

## Supported IDEs and Editors

This configuration works with any editor that supports EditorConfig, including:

-   Visual Studio (2017+)
-   Visual Studio Code
-   Rider
-   Sublime Text
-   Atom
-   Vim/Neovim
-   Emacs
-   And many others

## Usage

1. **Automatic**: Most modern IDEs automatically detect and apply EditorConfig rules
2. **Manual**: Some editors may require installing the EditorConfig extension
3. **Verification**: Use your IDE's code formatting tools to ensure compliance

## Customization

To modify these rules:

1. Edit the `.editorconfig` file
2. Changes apply to all files in the project
3. Some rules can be overridden in specific file sections
4. Severity levels can be adjusted (error, warning, suggestion, silent, none)

## Integration with Other Tools

This EditorConfig works alongside:

-   **StyleCop**: Enforces additional C# coding standards
-   **Code Analysis**: Integrates with .NET analyzers
-   **Build Tools**: Can be enforced during CI/CD pipelines
-   **Code Review**: Helps maintain consistent code quality

## Troubleshooting

If EditorConfig rules aren't being applied:

1. Ensure your IDE has EditorConfig support enabled
2. Check that the `.editorconfig` file is in the project root
3. Verify the file syntax is correct
4. Restart your IDE after making changes
5. Check IDE-specific EditorConfig settings

## Contributing

When contributing to this project:

1. Follow the established EditorConfig rules
2. Don't disable rules without team discussion
3. Use your IDE's auto-formatting features
4. Ensure all code passes the configured analyzers

## References

-   [EditorConfig Official Documentation](https://editorconfig.org/)
-   [.NET Code Style Rules](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/)
-   [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
-   [StyleCop Documentation](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)

---

_This EditorConfig ensures consistent, high-quality code across the SteamTrade project while maintaining modern C# best practices and performance optimizations._
