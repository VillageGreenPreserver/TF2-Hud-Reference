# Panel list

This is a list of panel types and their parameters.


## Panel
The most basic panel, all other panels derive from this.
Parameter | Data Type | Info
--------- | --------- | ----
fieldName | string | Renames the panel
xpos | pos |Position of the panel in the X axis
ypos | pos | Position of the panel in the Y axis
zpos | int | Render priority of the panel
wide | size | Size of the panel in the X axis
tall | size | Size of the panel in the Y axis
visible | bool | Visibility of the panel
enabled | bool | Changes the colour of labels and disables interaction with buttons, sliders, text boxes etc.
proportionalToParent | bool | Position & size values relative to the parent size, instead of screen size
fgcolor_override | color | Foreground colour
bgcolor_override | color | Background colour
alpha | int | Opacity of the panel 0-255
paintbackground | bool | Should the background be painted
PaintBackgroundType | int | How the background should be painted. Textures can be changed with Texture*</br>0 = Square corners</br>1 = Textured (Uses Texture1)</br>2 = Rounded corners</br>3 = Rounded Corners with horizontal fade
Texture1 | material | Top left
Texture2 | material | Top Right
Texture3 | material | Botttom Right
Texture4 | material | Bottom Left
RoundedCorners | int | Which corners are rounded
paintborder | bool | Should the panel have a border
border | border | What border to use
pin_to_sibling | string | Pin the panel's position to another panel on the same level in the hierarchy
pin_corner_to_sibling | int | Which corner should be pinned to the sibling
pin_to_sibling_corner | int | To which corner of the sibling should the panel be pinned
mouseinputenabled | bool | Should the panel listen for mouse inputs
keyboardinputenabled | bool | Should the panel listen for keyboard inputs
tooltiptext | string | Text to display when hovering over the panel
actionsignallevel | int | Allows nested child buttons to add their distant parents as action signal targets
IgnoreScheme | int
usetitlesafe | int
ForceStereoRenderToFrameBuffer | bool
tabPosition | int
autoResize | int
PinCorner | int
PinnedCornerOffSetX | int
PinnedCornerOffSetY | int
UnpinnedCornerOffSetX | int
UnpinnedCornerOffSetY | int
navUp | string
navDown | string
navLeft | string
navRight | string
navToRelay | string
navActivate | string
navBack | string

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Panel.FgColor
  | Panel.BgColor 


## EditablePanel
A panel that can have other panels inside of it. Derives from Panel.
Parameter | Data Type
--------- | ---------
skip_autoresize | bool
eatmouseinput | bool
showtooltipswhenmousedisabled | bool


## Frame
Derives from EditablePanel.
Parameter | Data Type
--------- | ---------
setclosebuttonvisible | bool
settitlebarvisible | bool
title | string
title_font | font
clientinsetx_override | int
titletextinsetX | int
titletextinsetY | int
infocus_bgcolor_override | color
outoffocus_bgcolor_override | color
titlebarbgcolor_override | color
titlebardisabledbgcolor_override | color
titlebarfgcolor_override | color
titlebardisabledfgcolor_override | color
frame_topGrip{} | ControlName: GripPanel
frame_bottomGrip{} | ControlName: GripPanel
frame_leftGrip{} | ControlName: GripPanel
frame_rightGrip{} | ControlName: GripPanel
frame_tlGrip{} | ControlName: GripPanel
frame_trGrip{} | ControlName: GripPanel
frame_blGrip{} | ControlName: GripPanel
frame_brGrip{} | ControlName: GripPanel
frame_caption{} | ControlName: CaptionGripPanel
frame_minimize{} | ControlName: FrameButton
frame_maximize{} | ControlName: FrameButton
frame_mintosystray{} | ControlName: FrameButton
frame_close{} | ControlName: FrameButton
frame_menu{} | ControlName: FrameSystemButton

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
FrameTitleBar.SmallFont | FrameTitleBar.TextColor | FrameBorder | Frame.TransitionEffectTime
FrameTitleBar.Font | FrameTitleBar.BgColor | | Frame.FocusTransitionEffectTime
 MarlettSmall | FrameTitleBar.DisabledTextColor | | Frame.ClientInsetX
 Marlett | FrameTitleBar.DisabledBgColor | | Frame.ClientInsetY
   | Frame.BgColor | | Frame.TitleTextInsetX
   | Frame.OutOfFocusBgColor


### GripPanel
Derives from Panel.

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
MarlettSmall | FrameGrip.Color1 |   | Frame.AutoSnapRange
Marlett | FrameGrip.Color2
   | FrameTitleBar.DisabledTextColor
   | FrameTitleBar.DisabledBgColor


### FrameButton
Derives from Button.

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   | FrameTitleButton.FgColor | TitleButtonBorder
   | FrameTitleButton.BgColor | TitleButtonDepressedBorder
   | FrameTitleButton.DisabledFgColor | TitleButtonDisabledBorder
   | FrameTitleButton.DisabledBgColor


### FrameSystemButton
Derives from MenuButton.

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   | FrameSystemButton.FgColor |  | FrameSystemButton.Icon
   | FrameSystemButton.BgColor | | FrameSystemButton.DisabledIcon


## PropertySheet
Derives from EditablePanel.
Parameter | Data Type
--------- | ---------
tabxindent | int
tabxdelta | int
tabxfittotext | bool
tabheight | int
tabheight_small | int
tabwidth | int
transition_time | float
tabskv{} | Controlname: PageTab

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
DefaultVerySmall |  | PropertySheetBorder | PropertySheet.TransitionEffectTime
Default |


### PageTab
Derives from Button.
Parameter | Data Type
--------- | ---------
selectedcolor | color
unselectedcolor | color
activeborder_override | border
normalborder_override | border

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
DefaultVerySmall | PropertySheet.SelectedTextColor | TabActiveBorder | PropertySheet.TransitionEffectTime
Default | PropertySheet.TextColor | TabBorder


## ScrollableEditablePanel
Derives from EditablePanel.
Parameter | Data Type
--------- | ---------
ScrollBar{} | ControlName: ScrollBar


## CExScrollingEditablePanel
A panel that can have other panels inside of it and can be scrolled. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
allow_mouse_wheel_to_scroll | bool | Only allow scrolling by dragging the slider
scroll_step | int | How much the scroll wheel scrolls
bottom_buffer | int | How much space to leave at the bottom
restrict_width | bool | Make the contents fit inside the panel
ScrollBar{} | ControlName: CExScrollBar


## CScrollableList
Derives from CExScrollingEditablePanel


## CExpandablePanel
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
resize_time | float | How quickly to resize panel
collapsed_height | int | How tall when collapsed
expanded_height | int | How tall when expanded


## ListPanel
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----

Default scheme values
Font | Color | Border
---- | ----  | ------
Default | ListPanel.BgColor | ButtonDepressedBorder
  | ListPanel.TextColor
   | ListPanel.DisabledTextColor
   | ListPanel.SelectedTextColor
   | ListPanel.DisabledSelectedTextColor
   | ListPanel.EmptyListInfoTextColor


## SectionedListPanel
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
show_columns | bool
linespacing | int
sectiongap | int
linegap | int

Default scheme values
Font | Color | Border
---- | ----  | ------
DefaultVerySmall | SectionedListPanel.HeaderTextColor | ButtonDepressedBorder
SectionedListPanel.Font | SectionedListPanel.DividerColor
   | SectionedListPanelHeader.BgColor
   | SectionedListPanel.BrightTextColor
   | SectionedListPanel.SelectedTextColor
   | SectionedListPanel.OutOfFocusSelectedTextColor
   | SectionedListPanel.SelectedBgColor
   | SectionedListPanel.TextColor
   | SectionedListPanel.BgColor
   | SectionedListPanel.OutOfFocusSelectedBgColor
   | SectionedListPanel.Font


## TFSectionedListPanel
Derives from SectionedListPanel.
Parameter | Data Type | Info
--------- | --------- | ----
medal_width | size
avatar_width | size
spacer | size
name_width | size
class_width | size
award_width | size
stats_width | size
horiz_inset | size


## PanelListPanel
Derives from EditablePanel.
Parameter | Data Type
--------- | ---------
autohide_scrollbar | bool

Default scheme values
Font | Color | Border
---- | ----  | ------
  | ListPanel.BgColor | ButtonDepressedBorder

## CBaseASyncPanel
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
refresh_delay | float
asynchandling | string | "content" or "loading", not actually on the panel but rather on the panel's child


## CTFLeaderboardPanel
Derives from CBaseASyncPanel.
Parameter | Data Type
--------- | ---------
entry_step | int
EvenTextColor | color
OddTextColor | color
LocalPlayerTextColor | color
ScoresContainer{} | ControlName: EditablePanel


## CLadderLobbyLeaderboard
Derives from CTFLeaderboardPanel.


## Menu
Derives from Panel.

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Menu.TextColor | MenuBorder
  | Menu.BgColor | 
  | BorderDark | 


### MenuSeparator
Derives from Panel.

Default scheme values
Font | Color | Border
---- | ----  | ------
  | Menu.SeparatorColor | 
  | Menu.BgColor | 




## Label
A panel with text. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
labelText | string | Text to display
font | font | What font to use
textAlignment | string | Where the text should align
textinsetx | int | Move text in X axis
textinsety | int | Move text in Y axis
use_proportional_insets | bool | Insets are proportional to screen size
wrap | bool | Should the text wrap when exceeding panel bounds
centerwrap | bool |Same as above but centered
auto_wide_tocontents | bool | The panel's wide value is automatically changed to fit the text
auto_tall_tocontents | bool | The panel's tall value is automatically changed to fit the text
allcaps | bool | Use only uppercase letters
disabledfgcolor2_override | color | Foreground colour when enabled == 0
dulltext | bool | Should the text use dull colours
brighttext | bool | Should the text use bright colours
associate | string

Default scheme values
Font | Color | Border
---- | ----  | ------
Default | Label.DisabledFgColor1
   | Label.DisabledFgColor2
   | Label.BgColor
   | Label.TextDullColor
   | Label.TextBrightColor
   | Label.TextColor
   | Label.SelectedTextColor


## CExLabel
An expanded label. Derives from Label.
Parameter | Data Type | Info
--------- | --------- | ----
fgcolor | color | Foreground colour


## Button
A panel that can fire a command when activated. Derives from Label.
Parameter | Data Type | Info
--------- | --------- | ----
command | string | Command of the button
selected | bool | Draws selected by default
stayselectedonclick | bool | When clicked on, sets selected to 1
stay_armed_on_click | bool | Don't revert back to default state when clicked
button_activation_type | int | How the button behaves</br>0 = When pressed sets depressed colours and activates command when released</br>1 = Activates command when pressed</br>2 = Activates command when released, doesn't set selected colours
sound_armed | sound | Sound when hovered over
sound_depressed | sound | Sound when pressing button
sound_released | sound | Sound when releasing button
defaultFgColor_override | color | Foreground colour
defaultBgColor_override | color |Background colour
armedFgColor_override | color | Foreground colour when hovered
armedBgColor_override | color | Background colour when hovered
depressedFgColor_override | color | Foreground colour when clicked on
depressedBgColor_override | color | Background colour when clicked on
selectedFgColor_override | color | Foreground colour when selected
selectedBgColor_override | color | Background colour when selected
keyboardFocusColor_override | color
blinkFgColor_override | color
default | bool

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Button.TextColor | ButtonBorder
   | Button.BgColor | ButtonDepressedBorder
   | Button.ArmedTextColor | ButtonKeyFocusBorder
   | Button.ArmedBgColor
   | Button.SelectedTextColor
   | Button.SelectedBgColor
   | Button.DepressedTextColor
   | Button.DepressedBgColor
   | Button.FocusBorderColor
   | Button.BlinkColor


## CExButton
Expanded button. Derives from Button.
Parameter | Data Type | Info
--------- | --------- | ----
fgcolor | color | Foreground colour
border_default | border | Default border
border_armed | border | Border when hovered
border_disabled | border | Border when enabled == 0
border_selected | border | Border when selected == 1


## CExImageButton
A button that displays an image. Derives from CExButton.
Parameter | Data Type | Info
--------- | --------- | ----
image_drawcolor | color | What colour to draw the image by default, can't use clientscheme entries
image_armedcolor | color | What colour to draw the image when hovered, can't use clientscheme entries
image_depressedcolor | color | What colour to draw the image when pressed, can't use clientscheme entries
image_disabledcolor | color | What colour to draw the image when enabled == 0, can't use clientscheme entries
image_selectedcolor | color | What colour to draw the image when selected == 1, can't use clientscheme entries
image_default | material | What image to use by default
image_armed | material | What image to use when hovered
image_selected | material | What image to use when selected == 1
SubImage{} | ControlName: ImagePanel


## CImageButton
A button that displays an image. Derives from Button.
Parameter | Data Type | Info
--------- | --------- | ----
scaleImage | bool | Whether to scale the image
inactiveimage | material | Image to use by default
activeimage | material | Image to use when hovered
inactivedrawcolor | color | What colour to draw the image by default
activedrawcolor | color | What colour to draw the image when hovered

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Button.TextColor | NoBorder
   | Button.ArmedTextColor
   | Button.DepressedTextColor


## ToggleButton
A button that can be toggled on and off. Derives from Button.

Default scheme values
Font | Color | Border
---- | ----- | ------
   | ToggleButton.SelectedTextColor |


## CheckButton
A button that looks like a checkbox. Derives from ToggleButton.
Parameter | Data Type | Info
--------- | --------- | ----
smallcheckimage | bool | Use a smaller check image

Default scheme values
Font | Color | Border
---- | ----  | ------
 MarlettSmall | CheckButton.TextColor | ButtonBorder
 Marlett | CheckButton.BgColor | ButtonDepressedBorder
   | CheckButton.Border1 | ButtonKeyFocusBorder
   | CheckButton.Border2
   | CheckButton.Check
   | CheckButton.SelectedTextColor
   | CheckButton.DisabledFgColor
   | CheckButton.DisabledBgColor
   | CheckButton.ArmedBgColor
   | CheckButton.DepressedBgColor
   | CheckButton.HighlightFgColor


## CvarToggleCheckButton
A checkbutton that displays the value of a cvar. Derives from CheckButton.
Parameter | Data Type | Info
--------- | --------- | ----
cvar_name | string
cvar_value | bool


## CExCheckButton 
Derives from CheckButton.


## ExpandButton
A button that looks like an arrow. Derives from ToggleButton.

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ExpandButton.Color


## CTFTeamButton
A button that animates a model. Animation events are called idle_enabled, idle_disabled, enter_enabled, enter_disabled, exit_enabled, exit_disabled & hover_disabled. Only works in the team select menu. Derives from CExButton.
Parameter | Data Type | Info
--------- | --------- | ----
associated_model | string | What model to animate
team | int
hover | float | Delay before animation


## CAutoFittingLabel
A label that changes the font to fit in the boundaries of the panel. Derives from Label.
Parameter | Data Type | Info
--------- | --------- | ----
fonts{}
```
"fonts"
{
  "1"
  {
    "font"  "large_font"
  }
  "2"
  {
    "font"  "medium_font"
  }
  "3"
  {
    "font"  "small_font"
  }
}
```


## URLLabel
A button that opens a web page. Derives from Label.
Parameter | Data Type | Info
--------- | --------- | ----
URLText | string | URL to the web page

Default scheme values
Font | Color | Border
---- | ----  | ------
 DefaultUnderline 


## RichText
A panel with text that can scroll and can use a text file for its contents. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
text | string | Text to display
textfile | path | A text file to display eg. "resource/text.txt"
scrollbar | bool | Should the scrollbar be enabled
maxchars | int
ScrollBar{} | ControlName: ScrollBar

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
 Default | RichText.TextColor |   | RichText.InsetX
 DefaultUnderline | RichText.BgColor | 
   | RichText.SelectedTextColor | 
   | RichText.SelectedBgColor | 


## CExRichText
An expanded rich text. Derives from RichText.
Parameter | Data Type | Info
--------- | --------- | ----
font | font | What font to use
fgcolor | color | Foreground colour
image_up_arrow | color | Image for the scrollbar's up arrow
image_down_arrow | color | Image for the scrollbar's down arrow
image_line | color | Image for the scrollbar slider's background 
image_box | color | Image for the scrollbar slider
image_up_arrow_mouseover | color | Image for the scrollbar's up arrow when hovered
image_down_arrow_mouseover | color | Image for the scrollbar's down arrow when hovered
Line{} | ControlName: ImagePanel
Box{} | ControlName: ImagePanel
UpArrow{} | ControlName: CExImageButton
DownArrow{} | ControlName: CExImageButton
ScrollBar{} | ControlName: ScrollBar

Default scheme values
Font | Color | Border
---- | ----  | ------
   | Blank | NoBorder


## CRichTextWithScrollbarBorders
Same as above but uses borders instead of images for image_line & image_box. "Line" & "Box" are Panels instead of ImagePanels. Derives from CExRichText.


## CEconItemDetailsRichText
"Rich text control that knows how to fill itself with information that describes a specific item definition." Derives from CRichTextWithScrollbarBorders.
Parameter | Data Type | Info
--------- | --------- | ----
highlight_color | color
itemset_color | color
link_color | color


## ScrollBar
A scrollbar. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
nobuttons | bool | Removes up & down buttons
autohide_buttons | bool | Automatically removes up & down buttons when not needed
Slider{} | ControlName: ScrollBarSlider
UpButton{} | ControlName: ScrollBarButton
DownButton{} | ControlName: ScrollBarButton

Default scheme values
Font | Color | Border | Other
---- | ----  | ------ | -----
   |   |   | ScrollBar.Wide


### ScrollBarSlider
The slider of a scrollbar. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
ButtonBorder | border | Border of the slider. Only works with IgnoreScheme 1

Default scheme values
Font | Color | Border
---- | ----  | ------
   | ScrollBarSlider.FgColor | ScrollBarSliderBorder
   | ScrollBarSlider.BgColor | ButtonBorder


### ScrollBarButton
Derives from Button.

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ScrollBarButton.FgColor | ScrollBarButtonBorder
   | ScrollBarButton.BgColor | ScrollBarButtonDepressedBorder
   | ScrollBarButton.ArmedFgColor | 
   | ScrollBarButton.ArmedBgColor | 
   | ScrollBarButton.DepressedFgColor | 
   | ScrollBarButton.DepressedBgColor | 


## CExScrollBar
"A scroll bar that can have specified width" (?)


## ImagePanel
A panel that displays an image. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
image | material | The image to display
fillcolor | color | Background colour
drawcolor | color | What colour to draw the image with
scaleImage | bool | Whether to scale the image
scaleAmount | float | How much to scale the image, set to 0 for full size
tileImage | bool | Repeat the image endlessly
tileHorizontally | bool | Repeat the image endlessly in the X axis
tileVertically | bool | Repeat the image endlessly in the Y axis
rotation | int | Rotate image in 90 degree increments
positionImage | bool


## ScalableImagePanel
A panel that displays an image. Can have scalable corners & sides. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
image | material | The image to display
drawcolor | color | What colour to draw the image with
src_corner_width | int | How big the texture's corners are in the X axis
src_corner_height | int | How big the texture's corners are in the Y axis
draw_corner_width | int | How big to draw the corners in the X axis
draw_corner_height | int | How big to draw the corners in the Y axis


## CTFImagePanel
An image panel that can be team coloured. Derives from ScalableImagePanel
Parameter | Data Type | Info
--------- | --------- | ----
teambg_0 | material | Image when unassigned
teambg_1 | material | Image on spectate
teambg_2 | material | Image on RED
teambg_3 | material | Image on BLU


## CIconPanel
A panel that displays an icon from scripts/mod_textures.txt. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
icon | icon | What icon to use
iconColor | color | What colour to draw the icon with
scaleImage | bool | Should the icon scale with the panel


## CAvatarImagePanel
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
scaleImage | bool
color_outline | color


## CBitmapPanel
Parameter | Data Type | Info
--------- | --------- | ----
material | material | Looks in materials/ instead of materials/vgui/
color | color


## CBitmapImagePanel
An image that can maintain its aspect ratio when resized. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
image | material | The image to display
imagecolor | color | What colour to draw the image with
imageAlignment | string | Where the image should align, uses same values as textAlignment
preserveAspectRatio | bool | Should the aspect ratio be maintained
filtered | bool


## CTFLogoPanel
A rotating TF logo.
Parameter | Data Type | Info
--------- | --------- | ----
radius | bool | Size of the logo
velocity | float | Speed of the logo



## TextEntry
A panel you can type text in. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
font | font | What font to use
textHidden | bool | Censor the text
editable | bool | Allow the user to change the text
maxchars | int | Maximum amount of characters allowed
NumericInputOnly | bool | Only allow numbers
selectallonfirstfocus | bool
unicode | bool
disabledFgColor_override | color
disabledBgColor_override | color
selectionColor_override | color
selectionTextColor_override | color
defaultSelectionBG2Color_override | color

Default scheme values
Font | Color | Border
---- | ----  | ------
 Default | TextEntry.TextColor | ButtonDepressedBorder
 DefaultVerySmall | TextEntry.BgColor | 
   | TextEntry.CursorColor | 
   | TextEntry.DisabledTextColor | 
   | TextEntry.DisabledBgColor | 
   | TextEntry.SelectedTextColor | 
   | TextEntry.SelectedBgColor | 
   | TextEntry.OutOfFocusSelectedBgColor | 
   | TextEntry.FocusEdgeColor | 


## ComboBox
A panel with a drop down list. Derives from TextEntry.
Parameter | Data Type | Info
--------- | --------- | ----
border_override | border | Changes the border
Button{} | ControlName: ComboBoxButton

Default scheme values
Font | Color | Border
---- | ----  | ------
   |   | ComboBoxBorder

### ComboBoxButton
Derives from Button.

Default scheme values
Font | Color | Border
---- | ----  | ------
 Marlett | ComboBoxButton.ArrowColor | ScrollBarButtonBorder
   | ComboBoxButton.BgColor | 
   | ComboBoxButton.ArmedArrowColor | 
   | ComboBoxButton.DisabledBgColor | 
   


## Slider
A panel with a movable slider. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
leftText | string | Text on the left
rightText | string | Text on the right
thumbwidth | int | Width of the slider
numTicks | int | Number of lines along the slider
rangeMin | int | What value the slider starts at
rangeMax | int | What value the slider ends at

Default scheme values
Font | Color | Border
---- | ----  | ------
 DefaultVerySmall | Slider.NobColor | ButtonBorder
   | Slider.TextColor | ButtonDepressedBorder
   | Slider.TrackColor | 
   | Slider.DisabledTextColor1 | 
   | Slider.DisabledTextColor2 | 


## CCVarSlider
A slider that can change a cvar. Derives from Slider
Parameter | Data Type | Info
--------- | --------- | ----
minvalue | float | Minimum value allowed
maxvalue | float | Maximum value allowed
cvar_name | string | Cvar to change
use_convar_minmax | bool | Use the minvalue & maxvalue of the cvar instead
allowoutofrange


## ProgressBar
A segmented progress bar. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
variable | string | What to measure
progress | float


## ContinuousProgressBar
Derives from ProgressBar.


## CBuildingHealthBar
A progress bar that changes colour when below 50%. Derives from ProgressBar.

Default scheme values
Font | Color | Border
---- | ----  | ------
   | BuildingHealthBar.BgColor | 
   | BuildingHealthBar.Health | 
   | BuildingHealthBar.LowHealth | 


## CircularProgressBar
Derives from ProgressBar
Parameter | Data Type | Info
--------- | --------- | ----
fg_image | material | Image to use as the progress bar
bg_image | material | Image to use as the background



## RotatingProgressBar
Derives from ProgressBar
Parameter | Data Type | Info
--------- | --------- | ----
image | material | Image that rotates
rotating_x | float | X position of the image
rotating_y | float | Y position of the image
rotating_wide | float | Wide of the image
rotating_tall | float | Tall of the image
start_degrees | float | Rotation of the image when variable == 0
end_degrees | float | Rotation of the image when variable == 100
rot_origin_x_percent | float | X position of what point the image rotates around, float value 0.0 - 1.0
rot_origin_Y_percent | float | Y position of what point the image rotates around, float value 0.0 - 1.0
approach_speed | float | The speed of rotation


## CAccountPanel
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
delta_item_start_y | int
delta_item_end_y | int
delta_item_x | int
delta_item_end_x | int
bg_texture | material
bg_image_x | int
bg_image_y | int
bg_image_wide | int
bg_image_tall | int
PositiveColor | color
NegativeColor | color
EventColor | color
RedRobotScoreColor | color
BlueRobotScoreColor | color
delta_lifetime | float
delta_item_font | font
delta_item_font_big | font
negative_flip_dir | bool


## CModelPanel
A panel that shows a 3D model. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
fov | int | FOV of the model
start_framed | bool
allow_offscreen | bool
model{}

The following parameters need to be in model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname | string | What model to use
modelname_hwm | string
skin | int | Which skin to use
angles_x | float | Rotation around X axis
angles_y | float | Rotation around Y axis
angles_z | float | Rotation around Z axis
origin_x | float | Position in the X axis
origin_y | float | Position in the Y axis
origin_z | float | Position in the Z axis
frame_origin_x | float
frame_origin_y | float
frame_origin_z | float
vcd | string
spotlight | bool
animation{} | | Animations of the model
attached_model{} | | Attach another model eg. a gun

The following parameters need to be in animation{}
Parameter | Data Type | Info
--------- | --------- | ----
name | string
sequence | string
activity | string
default | bool
pose_parameters{}

The following parameters need to be in attached_model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname | string
skin | int


## CPotteryWheelPanel
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
useparentbg | bool
lights{}

The following parameters need to be in lights{}
Parameter | Data Type | Info
--------- | --------- | ----
name | string | Accepts "directional", "point" or "spot"
color | color
direction | vector | directional & spot
attenuation | vector | point & spot
origin | vector | point & spot
maxDistance | float | point & spot
inner_cone_angle | float | spot
outer_cone_angle | float | spot
exponent | float | spot

```
"lights"
{
	"1"
	{
		"name"	"directional"
		"color"	"10 10 10"
		"direction" "0 0 0"
	}
}
```


## CMDLPanel
Derives from CPotteryWheelPanel.


## CBaseModelPanel
Derives from CMDLPanel
Parameter | Data Type | Info
--------- | --------- | ----
render_texture
use_particle
start_framed
disable_manipulation
fov
allow_rot
allow_pitch
allow_manip
max_pitch
model{}

The following parameters need to be in model{}
Parameter | Data Type | Info
--------- | --------- | ----
force_pos
modelname | What model to use
modelname_hwm
skin | Which skin to use
angles_x | Rotation around X axis
angles_y | Rotation around Y axis
angles_z | Rotation around Z axis
origin_x | Position in the X axis
origin_y | Position in the Y axis
origin_z | Position in the Z axis
frame_origin_x
frame_origin_y
frame_origin_z
vcd
spotlight
animation{} | Animations of the model
attached_model{} | Attach another model eg. a gun

The following parameters need to be in animation{}
Parameter | Data Type | Info
--------- | --------- | ----
name 
sequence
activity
default
pose_parameters{}

The following parameters need to be in attached_model{}
Parameter | Data Type | Info
--------- | --------- | ----
modelname
skin


## CTFPlayerModelPanel
Derives from CBaseModelPanel.
Parameter | Data Type | Info
--------- | --------- | ----
disable_speak_event |
customclassdata{} | Allows you to set fov, origin and angles for each class individually


## CItemModelPanel
A panel that show an item. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
special_attributes_only
model_xpos | Position of the model in the X axis
model_ypos | Position of the model in the Y axis
model_wide | Wide of the model
model_tall | Tall of the model
model_center_x | Center the model in the X axis
model_center_y | Center the model in the Y axis
tf2_icon_offset_x
tf2_icon_offset_y
noitem_use_fullpanel
text_center | Center the text in the Y axis
text_center_x | Center the text in the X axis
use_item_sounds
name_only | Don't show the stats of the item
attrib_only | Don't show the name of the item
model_only | Don't show the name or the stats of the item
model_hide | Don't show the model
paint_icon_hide
resize_to_text 
name_label_alignment
text_xpos | Position of the text in the X axis
text_ypos | Position of the text in the Y axis
text_wide | Wide of the text
text_yoffset
padding_height
max_text_height
text_forcesize
inset_eq_x | Equipped label X position
inset_eq_y | Equipped label Y position
standard_text_color
is_mouseover
wide
tall
collection_list_xpos
text_xpos_collection
hide_collection_panel
hide_modifier_icons


### CEmbeddedItemModelPanel
Model panel inside CItemModelPanel. Derives from CBaseModelPanel.
Parameter | Data Type | Info
--------- | --------- | ----
force_use_model
use_item_rendertarget
inventory_image_type
force_square_image
model_rotate_yaw_speed
use_pedestal


## CTFParticlePanel
A panel that displays a particle effect. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
ParticleEffects{}

The following parameters need to be in ParticleEffects{}
Parameter | Data Type | Info
--------- | --------- | ----
particle_xpos | X position of the particle
particle_ypos | Y position of the particle
particle_scale | Scale of the prticle
loop | Loop the particle animation
start_activated | Activate the particle animation immediately
particleName | Name of the particle
angles | Rotation of the particle, takes 3 values
control_point* | Particle control point setting, takes 3 values. Replace * with the number of the control point

```
"ParticleEffects"
{
	"1"
	{
		"particle_xpos"	"0"
		"particle_ypos"	"0"
		"particle_scale"	"1.0"
		"loop"			"1"
		"start_activated"	"1"
		"particleName"	""
		"angles"		"0 0 0"
		"control_point0"	"4 2 0"
		"control_point1"	"6 9 6"
	}
}
```


## CDrawingPanel
A panel you can draw in. Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
linecolor | What colour the line should be
team_colors | Use team colours for the line


## CNavigationPanel
A panel that has a list of buttons. The command for the buttons is select_0, select_1, select_2 etc. The commands can be aliased to something else. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
auto_layout
auto_scale
display_vertically
auto_layout_horizontal_buffer
auto_layout_vertical_buffer
selected_button_default
ButtonSettings{} | Settings for the buttons to use
Buttons{} | List of buttons


## CTFVideoPanel
Parameter | Data Type | Info
--------- | --------- | ----
command
start_delay
end_delay


## CTFArrowPanel
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----


## CTFPlayerPanel 
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
HealthIcon{} | ControlName: CTFPlayerPanelGUIHealth
ReadyBG{} | ControlName: ScalableImagePanel
ReadyImage{} | ControlName: ImagePanel



## CTFTeamStatus
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
team1_grow_dir
team2_grow_dir
max_size
6v6_gap
12v12_gap
team1_base_x
team1_max_expand
team2_base_x
team2_max_expand
playerpanels_kv{}


## CTFTeamStatusPlayerPanel
Derives from CTFPlayerPanel.
Parameter | Data Type | Info
--------- | --------- | ----
color_portrait_bg_red_local_player
color_portrait_bg_blue_local_player
color_portrait_bg_red
color_portrait_bg_blue
color_portrait_bg_red_dead
color_portrait_bg_blue_dead
color_bar_health_high
percentage_health_med
color_bar_health_med
percentage_health_low
color_bar_health_low
color_portrait_blend_dead_red
color_portrait_blend_dead_blue
healthbar{} | ControlName: ContinuousProgressBar
overhealbar{} | ControlName: ContinuousProgressBar
classimagebg{} | ControlName: Panel
DeathPanel{} | ControlName: ImagePanel


## CTFHudPlayerHealth
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
HealthBonusPosAdj
HealthDeathWarning
HealthDeathWarningColor



## CTFSpectatorGUIHealth
Derives from CTFHudPlayerHealth.



## CTFPlayerPanelGUIHealth
Derives from CTFSpectatorGUIHealth.



## CHudBaseDeathNotice
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
LineHeight | float
LineSpacing | float
CornerRadius | float
MaxDeathNotices | float
RightJustify | bool
TextFont | font
IconColor | color
BaseBackgroundColor | color
LocalBackgroundColor | color
KillStreakBackgroundColor | color


## CTFHudDeathNotice
Derives from CHudBaseDeathNotice.
Parameter | Data Type | Info
--------- | --------- | ----
TeamBlue | color
TeamRed | color
PurpleText | color
GreenText | color
LocalPlayerColor | color


## CPvPRankPanel
Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
matchgroup | MatchGroup_Ladder_6v6 or MatchGroup_Casual_12v12
show_type
show_name
show_model
show_progress
instantly_update
show_sources_when_hidden
xp_source_notification_center_x


## CMiniPvPRankPanel
Derives from CPvPRankPanel.


## CDashboardPartyMember
Parameter | Data Type | Info
--------- | --------- | ----
party_slot


## CMVMCriteriaPanel
Parameter | Data Type | Info
--------- | --------- | ----
challenge_spacer
challenge_name_width
challenge_skill_width
challenge_completed_size
challenge_map_width
challenge_map_height
has_ticket_width
squad_surplus_width
squad_surplus_width
badge_level_width
tour_name_width
tour_skill_width
tour_progress_width
tour_number_width


## CExplanationPopup
A speech bubble panel. Accepts button commands "close", "nextexplanation" & "prevexplanation". Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
next_explanation | Next speech bubble to draw
force_close | Disable the rest of the screen until this popup is closed
callout_inparents_x | X position of the speech bubble's tail
callout_inparents_y | Y position of the speech bubble's tail
start_x | X position before the expanding animation
start_y | y position before the expanding animation
start_wide | Wide before the expanding animation
start_tall | Tall before the expanding animation
end_x | X position after the expanding animation
end_y | y position after the expanding animation
end_wide | Wide after the expanding animation
end_tall | Tall after the expanding animation


## CRepeatingContainer
A panel that automatically positions its contents. Derives from EditablePanel.
Parameter | Data Type | Info
--------- | --------- | ----
spacing_method | How to space the panels. METHOD_STEP spaces them by a certain value, METHOD_EVEN spaces them evenly
x_step | Value to space the panels when using METHOD_STEP
IndividualSettings{} | Where you place the panels to be sorted
CommonSettings{} | What settings the panels should have by default

```
"Example"
{
  "ControlName"  "CRepeatingContainer"

  "IndividualSettings"
  {
    "Item1"
    {
      "ControlName"  "Label"
    }
    "Item2"
    {
      "ControlName"  "Label"
    }
    "Item3"
    {
      "ControlName"  "Label"
    }
  }

  "CommonSettings"
  {
    "fgcolor_override"  "69 69 69 255"
    "font"              "Default"
  }
}
```

## CLoadoutPresetPanel
Derives from EditablePanel
Parameter | Data Type | Info
--------- | --------- | ----
presetbutton_kv{}


## CCyclingAdContainerPanel
Derives from EditablePanel
Parameter | Data Type | Info
--------- | --------- | ----
items{}


## CItemAdPanel
Derives from EditablePanel
Parameter | Data Type | Info
--------- | --------- | ----
item
show_market
present_time


## CBuildingStatusAlertTray
Derives from Panel.
Parameter | Data Type | Info
--------- | --------- | ----
icon
deployed | Float 0.0 - 1.0


## CTFItemCardPanel
A leftover unused panel that uses Resource/UI/Econ/ItemCardPanel_Series1.res for its contents. Could be useful for a #base -esque reusable panel. Derives from EditablePanel
Parameter | Data Type | Info
--------- | --------- | ----
shadowoffset




