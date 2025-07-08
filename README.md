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


## 🧪 Installation
Unzip the Project 
Copy the "msg" class file into your project 


## 🧪 Demonstration 
The Zip is the whole project, including a Demo utility that gives you an interactive way of playing with all the arguments
and it gives comparison to the standard messagebox.show() 
and GUI buttons for browsing to custom image files for either the icon, or the picture 


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
```


## 🧪 Basic Usage

```vb.net
Dim newDialog As New Msg
newDialog.Box("Hello World")
```


## 🧪  Similar Usage compare to Messagebox.Show():

```vb.net
Dim newDialog As New Msg
newDialog.Box("Hello World", "Title", "Example Heading", "this is a footer message", MsgButtons.OK, MsgIcons.Information)
```


## 🧪 Advanced Usage

```vb.net
Dim newDialog As New Msg

customTheme = New Msg.MessageBoxTheme With {
        .BackColor = Color.White,
        .FontColor = Color.Black,
        .FooterColor = Color.Gray,
        .ButtonColor = Color.LightGray,
        .ButtonFontColor = Color.Black,
        .ButtonStyle = FlatStyle.Standard
    }

newDialog.Box("Hello World",
              "Title",
              "Example Heading",
              "this is a footer message",
              MsgButtons.OK,
              MsgIcons.Information,
              picture.image,
              defaultButton.OK,
              customTheme)
```


## 🧪 Examples 

Just a String "Test Message" <br>
<br>
![image](https://github.com/user-attachments/assets/43810655-d835-4095-a51a-409e28c2b609)


String With Icon <br>
<br>
![image](https://github.com/user-attachments/assets/6ec11b0e-b50e-4054-a177-8a9a4f4d4d81)


String, With Heading and Icon <Br>
<br>
![image](https://github.com/user-attachments/assets/8e045bc8-0d57-43c1-9b90-055b505f9c17)


specific icon for confirmation - more clear <br>
<br>
![image](https://github.com/user-attachments/assets/232f8c51-658b-4905-9fed-e4f67daccf5d)


Different Colour for Question (rather than reusing the same as 'information') <Br>
<br>
![image](https://github.com/user-attachments/assets/f5fbc84b-59bb-4e1d-b532-f4a9be8c00f3)


countdown with timed message <br>
<br>
![image](https://github.com/user-attachments/assets/31d24116-4f8f-4d50-b4b8-c594a1580ace)


Help button - with custom function assigned  <br>
<br>
![image](https://github.com/user-attachments/assets/10aa04df-0ec5-4b1b-91ef-550bf9717ecc)


Supports Richtext <br>
<br>
![image](https://github.com/user-attachments/assets/b43e1c0a-d8b6-48cd-a53c-c3db93b1a25b)


Optional Footer <br>
<br>
![image](https://github.com/user-attachments/assets/4ca5fcc3-d2b6-43cd-868b-6c8c7758fe93)


customizable themes (bakc colour, font colour, button colour, button font colour, and button style) <br>
<br>
![image](https://github.com/user-attachments/assets/a8424ba4-bc6c-401d-bf65-8be04ab62b12)


include a screenshot  <br>
<Br>
![image](https://github.com/user-attachments/assets/9bbebdeb-c805-4c5b-87cb-4f0a2bd3d31b)



