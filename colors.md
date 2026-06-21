#1C1A18
Editor Background

#201D1A
Sidebar Background

#181614
Activity Bar

#292521
Line Highlight

#3A342D
Selection

# White
- Variables
- Puncuation
- Operators
#D4CEC2

# Orange
- Functions
- Methods
#C7864A

# Blue
- Numbers
- Constants (literal constants)
  - true
  - false
  - nullptr
- Enum Members
#6D93B0

# Sandy Tan
- Parameters
- Member variables
#B49A78

# Yellow
- Strings
#C9B25F
or
#B9A055

# Red
- Language Keywords
  - if
  - else
  - for
  - while
  - switch
  - return
  - class
  - struct
  - enum
  - namespace
  - public
  - private
  - protected
  - constexpr
  - consteval
  - concept
  - requires
  - typedef
  - using
  - const
  - static
  - inline
  - virtual
  - override
  - final
  - noexcept
  - template
  - typename
  - decltype
  - auto
  - mutable
  - friend
#B05F4A

# Purple
- Macros
- Preprocessor
- C++ attributes and annotations
- vendor attributes
#8A749C

# Faded Rust
- namespace names
#7F6B6B

# Dark faded green (sage like?)
- Comments
#6F7D6B

# Steel
- User types
- Built-in types (int, uint32_t, float, etc.)
- alias name (using and typedef names)
- template types (<T>)
#8F98A1

# Phase 1: Create a minimal theme
Generate a theme extension.
Set:
editor background
UI backgrounds
syntax colors
semantic token colors
Test on:
Modern C++
Embedded C
Header files
Template-heavy code

# Phase 2: Fix semantic mappings

Phase 3: Tune contrast
After several hours of coding:
Is Steel distinguishable from Sandy Tan?
Are comments too visible?
Is Yellow too bright?
Are namespace chains distracting?

# Only then start tweaking colors.

# Create the theme
npm setup
`npm install -g yo generator-code`

generate:
`yo code`

select:
`New Color Theme`

1st JSON:
```
{
  "$schema": "vscode://schemas/color-theme",
  "name": "WALL-E Dust",

  "colors": {
    "editor.background": "#1C1A18",
    "sideBar.background": "#201D1A",
    "activityBar.background": "#181614",
    "editor.lineHighlightBackground": "#292521",
    "editor.selectionBackground": "#3A342D"
  },

  "tokenColors": [],
  "semanticTokenColors": {
    "variable": "#D4CEC2",
    "parameter": "#B49A78",
    "property": "#B49A78",
    "function": "#C7864A",
    "method": "#C7864A",
    "number": "#6D93B0",
    "enumMember": "#6D93B0",
    "string": "#B9A055",
    "comment": "#6F7D6B",
    "type": "#8F98A1",
    "class": "#8F98A1",
    "struct": "#8F98A1",
    "enum": "#8F98A1",
    "typeParameter": "#8F98A1",
    "namespace": "#7F6B6B",
    "macro": "#8A749C"
  }
}
```

text mate fallbacks:
```
{
  "scope": [
    "keyword.control",
    "keyword.operator.word"
  ],
  "settings": {
    "foreground": "#B05F4A"
  }
},
{
  "scope": [
    "entity.name.function"
  ],
  "settings": {
    "foreground": "#C7864A"
  }
},
{
  "scope": [
    "comment"
  ],
  "settings": {
    "foreground": "#6F7D6B"
  }
}
```

test code:
```
namespace hal::drivers
{
template<typename T>
class MotorController
{
public:
    constexpr void setSpeed(uint32_t rpm);

private:
    uint32_t currentSpeed_;

    static constexpr bool Enabled = true;
};
}
```
