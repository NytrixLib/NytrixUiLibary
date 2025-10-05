

```markdown
# Roblox UI Library

A comprehensive, feature-rich UI library for Roblox experiences built with Roblox Lua.

## 📋 Overview

This UI library provides a modern, customizable interface system for Roblox games with a wide range of interactive elements and smooth animations. The library features a draggable main window, organized category system, and various GUI components commonly used in Roblox applications.

## 🚀 Features

### Core Components
- **Draggable Main Window** - Fully customizable and movable interface
- **Category System** - Organized tab-based navigation
- **Section Management** - Left/Right panel organization
- **Responsive Design** - Adapts to different screen sizes

### UI Elements
- **Buttons** - Clickable buttons with hover and click effects
- **Checkboxes** - Toggleable options with visual feedback
- **Toggles** - Switch-style toggles with smooth animations
- **Textboxes** - Input fields with focus states
- **Keybinds** - Customizable key binding system
- **Color Pickers** - Advanced color selection with wheel and RGB/Hex input
- **Sliders** - Range input with visual progress indicators
- **Dropdowns** - Single and multi-select dropdown menus

### Additional Features
- **Notifications** - Custom notification system with auto-expire
- **Prompts** - User confirmation dialogs
- **Smooth Animations** - Exponential easing animations throughout
- **Hover Effects** - Visual feedback on all interactive elements
- **Customizable Themes** - Easy color and style customization

## 🛠 Installation

1. Clone this repository or download the script file
2. Insert the script into your Roblox game's `ServerScriptService` or `StarterGui`
3. Require the module in your scripts:

```lua
local UILibrary = require(path.to.UILibrary)
```

📖 Basic Usage

Initialization

```lua
local UI = UILibrary.new("Your Game Name", "UserID", "Rank")
```

Creating Categories and Sections

```lua
local mainCategory = UI:Category("Main", "rbxassetid://icon_image")
local tab = mainCategory:Button("Aimbot", "rbxassetid://tab_icon")

local leftSection = tab:Section("Aim Settings", "Left")
local rightSection = tab:Section("Visual Settings", "Right")
```

Adding UI Elements

```lua
-- Button
leftSection:Button({
    Title = "Enable Aimbot",
    Description = "Toggle aim assistance",
    ButtonName = "ACTIVATE"
}, function()
    print("Aimbot activated!")
end)

-- Toggle
leftSection:Toggle({
    Title = "Auto Fire",
    Description = "Automatically shoot at targets",
    Default = true
}, function(state)
    print("Auto fire:", state)
end)

-- Slider
leftSection:Slider({
    Title = "Aim Smoothing",
    Description = "Adjust aim smoothness",
    Min = 0,
    Max = 100,
    Default = 50
}, function(value)
    print("Smoothing set to:", value)
end)

-- Color Picker
rightSection:ColorPicker({
    Title = "Target Color",
    Description = "Color for target highlight"
}, function(color)
    print("Color selected:", color)
end)
```

🎨 Customization

Animation Speed

```lua
UI:setAnimSpeed(100) -- Adjust animation speed (default: 100)
```

Notifications

```lua
UI:Notification({
    Title = "Information",
    Desc = "This is a notification message",
    expire = 5 -- seconds
})
```

Prompts

```lua
local result = UI:Prompt({
    Title = "Confirmation",
    Desc = "Are you sure you want to continue?"
})
```

🔧 Advanced Features

Keybind System

```lua
local keybind = section:Keybind({
    Title = "Aim Key",
    Default = Enum.KeyCode.E
}, function()
    print("Aim key pressed!")
end)
```

Dropdown Menus

```lua
local dropdown = section:Dropdown({
    Title = "Target Selection",
    Options = {
        ["Closest"] = true,
        ["Farthest"] = false,
        ["Random"] = false
    },
    Multi = false -- Set to true for multi-select
}, function(selection)
    print("Selected:", selection)
end)
```

🏗 Architecture

The library uses a hierarchical structure:

```
Window
├── Categories
│   ├── Buttons (Tabs)
│   │   ├── Sections (Left/Right)
│   │   │   ├── UI Elements
│   │   │   └── More Elements...
```

📝 API Reference

Window Methods

· new(gameName, userId, rank) - Create new UI instance
· setAnimSpeed(speed) - Adjust animation timing
· Notification(settings) - Show notification
· Prompt(settings) - Show confirmation dialog
· ChangeCategory(name) - Switch active category
· ChangeCategorySelection(name) - Switch active tab

Element Methods

Each UI element returns an object with:

· getValue() - Get current value
· setValue(newValue) - Update value
· Element-specific methods

🔒 Compatibility

· Roblox Studio: Fully compatible
· Mobile Devices: Touch-friendly interface
· Tablets: Responsive design
· PC: Mouse and keyboard optimized

📄 License

This project is provided as-is for educational and development purposes. Please ensure compliance with Roblox's Terms of Service when using in production environments.

🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

⚠️ Disclaimer

This UI library is intended for legitimate Roblox game development. Users are responsible for ensuring their usage complies with Roblox's terms of service and community guidelines.

```

This README provides:
- Comprehensive overview of the library's capabilities
- Installation and usage instructions
- Code examples for all major features
- API documentation
- Architecture explanation
- Compatibility information
- Proper disclaimers for Roblox development

The documentation is structured to help developers quickly understand how to implement and customize the UI library in their Roblox projects.
```
