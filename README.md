# VB.Net-Lib-Msg
...Let me do, what Microsoft failed to do...for decades... 

Give you a **fully customizable dialog box** for .NET Framework 4.5.1+ intended as a complete replacement for `MessageBox.Show()`. This project removes the limitations of the traditional `System.Windows.Forms.MessageBox`, offering rich content support, extended features, modern styling, and total flexibility.

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
1. Unzip the project

2. in your own project, create a new Form, call it EXACTLY "Msg" (so "Msg.vb" in full) <Br>
Set the forms inital size to 380,190

4. in a seperate visual studio instance, open the VB.NET-Lib-Msg solution, select everything on the Msg Form, and paste it into your project's recreation of "Msg" <br>
(it all fits as long as you initlaly set the empty forms size to 380, 190)

5. Edit the Msg form in Your project

6. edit the Msg form in the VB.NET-Lib-Msg project, copy the whole Class and paste into yours overwriting your empty Msg class

7. go through your recreation of Msg's forms properties and set: <br>
   - backColour = white 
   - FormBorderStyle = FixedSingle
   - maximumSize = 800,600
   - maximizeBox = false
   - MinimumSize = 300, 160
   - ShowIcon = False
   - StartPosition = CenterToScreen
   - Text = ""
  
8. in the "msg" class, find this part: <br>
```vb.net
       Public Shared Sub LoadMsgIconImages()
        Dim assembly As Assembly = Assembly.GetExecutingAssembly()
        Dim baseNamespace As String = "Msg."
```
and edit the baseNameSpace: <br>
![image](https://github.com/user-attachments/assets/9519e5ad-d4c7-4a98-a4dd-d820c69d1bc8)

to match YOUR applications rootname space: <br>
![image](https://github.com/user-attachments/assets/4bc747aa-24e4-44db-94a1-b42e68f9fa91) <br>
(for the icons to work as theyre embedded resources) 
<br>
<br>

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
<Br>
<Br>
<Br>

## 🧪 Basic Usage

```vb.net
Dim newDialog As New Msg
newDialog.Box("Hello World")
```


## 🧪  Similar Usage compare to Messagebox.Show():

```vb.net
Dim newDialog As New Msg
newDialog.Box("Hello World", "Title", "Example Heading", "this is a footer message", Msg.ButtonOptions.OK, msg.GetMsgIcon(Msg.MsgIcon.Question))
```


##  🧪 Using an Icon (because this class uses image instead of icon, ive provided a function to convert it first)
```vb.net
Dim msg1 As New Msg
Dim tempIcon As Image = msg1.GetMsgIcon(Msg.MsgIcon.Question)
Dim result As Msg.DialogResultCustom = msg1.Box("Quit?", "Quit Application?", "Confirm:", "", Msg.ButtonOptions.YesNo, tempIcon, Nothing, Msg.DefaultButton.No)
```
screenshot example: <br>
![image](https://github.com/user-attachments/assets/4faa81b6-9d1d-4e7a-b0a1-1bbc7e325425)


##  🧪 Using it for an Error Dialog - where ex.message is main message, and stackTrace is the footer
(example below forces an error to demonstrate)
```vb.net
        Try
            Dim tempInt As Integer = 0
            Dim tempString As String = "zero"
            tempInt = tempString
        Catch ex As Exception
            Dim newFormInstance As New Msg
            Dim tempIcon As Image = newFormInstance.GetMsgIcon(Msg.MsgIcon.ErrorRed)
            newFormInstance.Box(ex.Message, "Error Getting Icon", "Error getting Icon from 'MsgIconImages' Dictionary:", ex.StackTrace, Msg.ButtonOptions.OK, tempIcon, Nothing, Msg.DefaultButton.OK, newFormInstance.customMsgTheme, Nothing, Nothing)
        End Try
```
screenshot example: <br>
![image](https://github.com/user-attachments/assets/752127b0-ab90-46c5-aa05-ab4d76b90781)




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

<Br>
<Br>
<br>

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


customizable themes (back colour, font colour, button colour, button font colour, and button style) <br>
<br>
![image](https://github.com/user-attachments/assets/a8424ba4-bc6c-401d-bf65-8be04ab62b12)


include a screenshot  <br>
<Br>
![image](https://github.com/user-attachments/assets/9bbebdeb-c805-4c5b-87cb-4f0a2bd3d31b)


Long Message - Not truncated, has auto-scroll bars <br>
<br>
![image](https://github.com/user-attachments/assets/4303484b-d405-4757-9710-acb76fb3832a)

