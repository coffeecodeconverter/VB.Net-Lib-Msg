# VB.Net-Lib-Msg
A **fully customizable dialog box** for .NET Framework 4.5.1+ intended as a complete replacement for `MessageBox.Show()`. This project removes the limitations of the traditional `System.Windows.Forms.MessageBox`, offering rich content support, extended features, modern styling, and total flexibility.

---

## 🚀 Requirements

- **.NET Framework 4.5.1 or higher**

---

## 📦 Features Overview

- ✅ RichText support for headings, messages, and footers
- 🖼️ Add custom icons or embedded pictures
- 🎨 Fully themeable and layout-customizable
- 🧭 Dynamic sizing and scrollable content
- ⏲️ Timed auto-close dialogs with countdowns
- 🆘 Optional Help button with custom function
- 🧠 IntelliSense-friendly with custom Enums and Classes
- 🖱️ Custom buttons and default button support
- 🖼️ Built-in and modern icon support, including "Confirmation" icon
- 💬 Layout auto-adjusts based on provided content
- 🧪 Fully extensible and easy to implement

---

## 🧠 Why MsgBox 2.0?

The built-in `.NET MessageBox` is limiting when you need to go beyond displaying a simple string. Whether you want enhanced formatting, better interaction, or just more control over the look and behavior, `Msg.Box()` brings the power and freedom you've been missing.

---

## 🔑 Key Features in Detail

- **RichText formatting**: Headings, messages, and footers all support RTF.
- **Custom Icons & Images**: Use system icons, high-res custom icons, or embed any image.
- **Custom Buttons**: Define your own button sets beyond the default.
- **Themes & Layouts**: Change color schemes, font colors, button styles, and layout.
- **Auto-sizing**: Dialog width and height adapt to your content length.
- **Auto-scroll**: Scrollbars appear if the content overflows, unlike the native MessageBox.
- **Timed Dialogs**: Close the message box automatically after a given duration (ms).
- **Help Button**: Optional button that runs a custom function. Automatically hidden if a duration is set.
- **Custom Position and Size**: Override defaults with `X`, `Y`, `Width`, and `Height`.
- **Fallback Behaviors**: Default buttons and icons are applied when not explicitly set.

---

## 🧪 Primary Function Signature

```vb.net
Box(
    message As String,
    title As String,
    heading As String,
    footer As String,
    buttonOption As MsgButtons,
    icon As MsgIcons,
    picture As Image,
    defaultButton As defaultButton,
    theme As MessageBoxTheme,
    helpFunction As Action,
    duration As Integer,
    X As Integer,
    Y As Integer,
    Width As Integer,
    Height As Integer,
    Layout As MsgLayout
) As DialogResultCustom

