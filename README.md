# SideBar-Component
Sidebar menu powered by a customizable collection and color configuration variables. This menu format is easy to replicate and expandable for use in other applications in a simplified manner

## Previews

![{8DE551DE-A110-402D-94A5-4392B635C5E3}](https://github.com/user-attachments/assets/d2dbaa20-58a0-4c32-8501-553f57067d3b)


## Procedure

### Step 1

Go to the “Component” screen and create a new component

![{F42EA843-9661-494E-B2D5-F613F71AA2DD}](https://github.com/user-attachments/assets/24d5ee3b-1115-4992-a15e-a65d6fd44e91)


### Step 2

In the properties tab, select “Access Application Scope”.

![image](https://github.com/user-attachments/assets/e7fee111-3011-43e8-a2c3-add86b0fbfa9)


### Step 3
Still in the properties screen, go to size and select the “Height” property. In the code bar, paste the code below: 
```App.Height```

![Captura de tela 2024-10-16 182126](https://github.com/user-attachments/assets/127503d8-3b7a-41bd-a170-efd6a5cc92ca)
![{20E2E3D6-87E9-4FAF-8597-95B5541739FB}](https://github.com/user-attachments/assets/e24ddfb1-5079-45e0-9680-913807756a5b)


### Step 4
Still in the properties screen, select the “Width” property. In the code bar, paste the code below: 
```If(!varNavOpen; 241; 100)```

![{8D8106D9-E36B-4EBC-97E9-2D49664478C2}](https://github.com/user-attachments/assets/53e03db2-d202-4ae5-b03f-a0c6e40080cd)
![{A6B525AC-96D8-4D08-818F-D4EAD1C31941}](https://github.com/user-attachments/assets/06f4cbb0-d07e-41f0-be59-a2672b9fa7c2)


**Note**: Don’t worry about the initial error message. After completing all the steps, the messages will disappear.

### Step 5
Paste the YAML code inside the created component.
```
- NavBar_Container_3:
    Control: GroupContainer
    Variant: verticalAutoLayoutContainer
    Properties:
      DropShadow: =DropShadow.None
      Fill: =ColorValue(varConfigColors.NavBar_Container_Color)
      Height: =Parent.Height
      LayoutAlignItems: =LayoutAlignItems.Stretch
      LayoutDirection: =LayoutDirection.Vertical
      LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
      LayoutMode: =LayoutMode.Auto
      RadiusBottomLeft: =0
      RadiusBottomRight: =0
      RadiusTopLeft: =0
      RadiusTopRight: =0
      Width: =If(varNavOpen,100,241)
    Children:
    - HeaderNavBar_Container_3:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          AlignInContainer: =AlignInContainer.SetByContainer
          DropShadow: =DropShadow.None
          FillPortions: =2
          LayoutAlignItems: =LayoutAlignItems.Stretch
          LayoutDirection: =LayoutDirection.Vertical
          LayoutJustifyContent: =LayoutJustifyContent.SpaceBetween
          LayoutMinWidth: =0
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =0
          RadiusBottomRight: =0
          RadiusTopLeft: =0
          RadiusTopRight: =0
          Width: =NavBar_Container_3.Width
        Children:
        - TitleNavBar_Container_3:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              AlignInContainer: =AlignInContainer.SetByContainer
              DropShadow: =DropShadow.None
              FillPortions: =2
              LayoutAlignItems: =LayoutAlignItems.Center
              LayoutGap: '=If(!varNavOpen, 24,0) '
              LayoutMinHeight: =49
              LayoutMinWidth: =0
              LayoutMode: =LayoutMode.Auto
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
              Width: =NavBar_Container_3.Width
            Children:
            - Label1_7:
                Control: Label
                Properties:
                  Text: ="Name Application"
                  Color: =RGBA(255, 255, 255, 1)
                  FontWeight: =FontWeight.Bold
                  Size: =12
                  Visible: '=If(!varNavOpen, true,false) '
            - Icon1_3:
                Control: Classic/Icon
                Variant: Hamburger
                Properties:
                  OnSelect: =Set(varNavOpen,!varNavOpen)
                  AlignInContainer: =AlignInContainer.Center
                  Color: =RGBA(255, 255, 255, 1)
                  FillPortions: =2
                  Height: =40
                  Icon: =Icon.Hamburger
                  LayoutMinWidth: =40
        - Perfil_Container_3:
            Control: GroupContainer
            Variant: verticalAutoLayoutContainer
            Properties:
              AlignInContainer: =AlignInContainer.SetByContainer
              DropShadow: =DropShadow.None
              FillPortions: =5
              LayoutAlignItems: =LayoutAlignItems.Center
              LayoutDirection: =LayoutDirection.Vertical
              LayoutJustifyContent: =LayoutJustifyContent.Center
              LayoutMinWidth: =0
              LayoutMode: =LayoutMode.Auto
              RadiusBottomLeft: =0
              RadiusBottomRight: =0
              RadiusTopLeft: =0
              RadiusTopRight: =0
              Width: =NavBar_Container_3.Width
            Children:
            - Image1_3:
                Control: Image
                Properties:
                  Image: =varUser.Picture
                  Height: =120
                  ImagePosition: =ImagePosition.Fill
                  RadiusBottomLeft: =70
                  RadiusBottomRight: =70
                  RadiusTopLeft: =70
                  RadiusTopRight: =70
                  Visible: '=If(!varNavOpen, true,false) '
                  Width: =120
            - Label1_11:
                Control: Label
                Properties:
                  Text: ="Olá, "& varUser.DisplayName
                  Color: =RGBA(255, 255, 255, 1)
                  FillPortions: =4
                  FontWeight: =FontWeight.Bold
                  Size: =12
                  Visible: '=If(!varNavOpen, true,false) '
    - NavBarMain_Container_3:
        Control: GroupContainer
        Variant: verticalAutoLayoutContainer
        Properties:
          AlignInContainer: =AlignInContainer.SetByContainer
          DropShadow: =DropShadow.None
          FillPortions: =4
          LayoutDirection: =LayoutDirection.Vertical
          LayoutMode: =LayoutMode.Auto
          RadiusBottomLeft: =0
          RadiusBottomRight: =0
          RadiusTopLeft: =0
          RadiusTopRight: =0
          Width: =NavBar_Container_3.Width
        Children:
        - Gallery4_3:
            Control: Gallery
            Variant: galleryVertical
            Properties:
              OnSelect: =Navigate(ThisItem.MenuScreenNavigate)
              Items: =colNavBarConfigs
              Layout: =Layout.Vertical
              LayoutMinHeight: =50
              LayoutMinWidth: =0
              ShowNavigation: =true
              ShowScrollbar: =false
              TemplateSize: =Self.Height/7
            Children:
            - NavigateButton:
                Control: Classic/Button
                Properties:
                  OnSelect: =Navigate(ThisItem.MenuNavigate)
                  Text: =""
                  Fill: =RGBA(0, 0, 0, 0)
                  Height: =64
                  HoverBorderColor: =ColorFade(ColorValue("#ffffff"), 20%)
                  HoverColor: =RGBA(0, 0, 0, 0)
                  HoverFill: =
                  Width: =Parent.TemplateWidth - 5
                  Y: =
            - NavBarConteudoBotões_Container_3:
                Control: GroupContainer
                Variant: horizontalAutoLayoutContainer
                Properties:
                  DropShadow: =DropShadow.None
                  Height: =64
                  LayoutMode: =LayoutMode.Auto
                  RadiusBottomLeft: =0
                  RadiusBottomRight: =0
                  RadiusTopLeft: =0
                  RadiusTopRight: =0
                  Width: =222
                Children:
                - Icon3_3:
                    Control: Classic/Icon
                    Variant: VerticalLine
                    Properties:
                      AlignInContainer: =AlignInContainer.Stretch
                      Color: =ColorValue(varConfigColors.NavBar_Selector)
                      Icon: =Icon.VerticalLine
                      LayoutMinWidth: =5
                      Visible: =If(App.ActiveScreen = ThisItem.MenuNavigate, true, false)
                      Width: =5
                - Icon2_7:
                    Control: Classic/Icon
                    Variant: Cars
                    Properties:
                      AlignInContainer: =AlignInContainer.Center
                      Color: =RGBA(255, 255, 255, 1)
                      Height: =41
                      Icon: =ThisItem.MenuIcon
                      LayoutMinHeight: =50
                - Label7_3:
                    Control: Label
                    Properties:
                      Text: =ThisItem.MenuLabel
                      AlignInContainer: =AlignInContainer.Stretch
                      Color: =RGBA(255, 255, 255, 1)
                      FillPortions: =5
                      FontWeight: =FontWeight.Bold
                      LayoutMinHeight: =20
                      LayoutMinWidth: =50
                      Visible: '=If(!varNavOpen,true,false) '
                - Icon2_6:
                    Control: Classic/Icon
                    Variant: Cars
                    Properties:
                      AlignInContainer: =AlignInContainer.Stretch
                      Color: =RGBA(255, 255, 255, 1)
                      Height: =50
                      Icon: =Icon.ChevronRight
                      LayoutMinHeight: =21
                      LayoutMinWidth: =15
                      Width: =25
```
![{5301BC2A-BE07-4F3D-AA74-FC5B00E78447}](https://github.com/user-attachments/assets/52f14de7-c553-4ab5-be51-7d50d59e83cc)
![{1C55ACDC-1D37-4BDD-A4E6-B680DA74635E}](https://github.com/user-attachments/assets/9e09aada-3d86-4d8f-a4f7-c1cfd3d76c38)
**Note**: Don’t worry about the initial error message. After completing all the steps, the messages will disappear.

### Step 6 
Go to Screens > App > Select the “OnStart” property and paste the code below:
```ClearCollect(
    colNavBarConfigs;
    {
        MenuLabel: "Home";
        MenuIcon: Icon.Home;
        MenuNavigate: App.ActiveScreen;
        MenuID: 1
    };
    {
        MenuLabel: "Screen2";
        MenuIcon: Icon.Paste;
        MenuNavigate: App.ActiveScreen;
        MenuID: 2
    };
    {
        MenuLabel: "Screen3";
        MenuIcon: Icon.AddDocument;
        MenuNavigate: App.ActiveScreen;
        MenuID: 3
    }
);;

Set(
    varConfigColors;
    {
        NavBar_Container_Color: "#2b3d41";
        NavBar_Bottom_Text_Colors: "#FFFFFF";
        NavBar_Icones_Colors: "#FFFFFF";
        NavBar_Selector:"#FFFFFF"
    }
);;

Set(
    varUser;
    {
        DisplayName: User().FullName;
        Claims: "i:0#.f|membership|" & Lower(User().Email);
        Department: "";
        Email: User().Email;
        JobTitle: "";
        Picture: User().Image
    }
)
```

![{C78C92BF-70DF-4636-945E-49AAF77E650C}](https://github.com/user-attachments/assets/bc62a9ff-b06b-4102-b485-9091e5f34ad3)
![{EFA0F8D6-50E0-4D7C-9FA3-B6CDEFF6823F}](https://github.com/user-attachments/assets/8ba7c9af-ac0d-4fd1-aef4-51bcce20146b)

**Note**:After pasting the code, select App again, right-click and select “Run OnStart” to execute the pasted code.

### Last Step
To add the menu, go to “Insert” in the top bar > Customizable > Select the created component.
![{1E605478-33EA-4DDF-8373-8CB91466543F}](https://github.com/user-attachments/assets/d2951e04-732c-406b-9c34-2e32e49f685e)

![{8DE551DE-A110-402D-94A5-4392B635C5E3}](https://github.com/user-attachments/assets/d2dbaa20-58a0-4c32-8501-553f57067d3b)

## Questions 1
To customize the color of the elements, use the variable **varConfigColor**.
```
Set(
    varConfigColors;
    {
        NavBar_Container_Color: "#2b3d41";
        NavBar_Bottom_Text_Colors: "#FFFFFF";
        NavBar_Icones_Colors: "#FFFFFF";
        NavBar_Selector:"#FFFFFF"
    }
);;
```

To add more elements to the menu, use the **colNavBarConfigs** collection,adding +1 to the ID. Just follow the template below:
```
 {
        MenuLabel: "Screen3";
        MenuIcon: Icon.AddDocument;
        MenuNavigate: App.ActiveScreen; 
        MenuID: 3
    }
```
