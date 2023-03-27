# User Interfaces
Written by Aoldri#9534
___
> Welcome to my little circle of hell: Making UI in S.T.A.L.K.E.R.
___

User Interfaces are the funny little things on-screen that you can either: interact with, like the inventory; or read to be informed of important gameplay elements, like your health bar.

There are three major components to any UI: Textures, Layout, and Scripts.

## Textures
This is what is actually drawn on screen, what gives every button its look, and every background its colour.

These are written in `.xml` files inside `configs/ui/textures_descr/` through "Texture Descriptions", in which every texture is a `texture` tag with the following attributes: a unique ID, an x and y coordinate, and their dimensions.

The `x`, `y`, `width`, and `height` are measured in pixels, relative to the top-left of the image (0,0).

Every texture should be a child element of a `file` tag, with a `name` attribute containing the path to the corresponding image.

Example:
```xml
<!-- configs/ui/textures_descr/ui_actor_dialog_screen.xml -->
<w>
    <file name="ui/ui_actor_dialog_screen">
	    <texture id="ui_inGame2_dialog_main_window" x="0" y="0" width="634" height="760" />
    </file>
</w>

```

Once complete, every defined texture description is now available for the [Layout](#layout) to use, through the `id`.

## Layout

This is how everything is organised on screen, determining how different elements are placed together, and specify their respective attributes.

These are written in `.xml` files inside `configs/ui/`.

The precise attributes and child elements that are available will be determined by the kind of [components](ui_classes.md) you decide to use.

That said, it's up to you on how to organise them within this file: A common theme is to nest elements depending on their parents, as their origin will be offset by the parent element's location.

Example:
```xml
<!-- configs/ui/ui_items_backpack_16.xml -->
<w>
	<backpack x="416" y="341" width="192" height="85" stretch="1" >
		<background x="0" y="0" width="192" height="85" stretch="1" >
			<texture>ui_inGame2_message_box</texture>
		</background>

		<btn_cancel x="28" y="52" width="56" height="28" stretch="1" check_mode="0">
			<text font="letterica16">ui_inv_cancel</text>
			<texture>ui_button_ordinary</texture>
		</btn_cancel>

		<btn_ok x="100" y="52" width="56" height="28" stretch="1" check_mode="0">
			<text font="letterica16">ui_inv_ok</text>
			<texture>ui_button_ordinary</texture>
		</btn_ok>

		<input x="12" y="20" width="160" height="30" stretch="1">
			<text x="4" font="letterica16" vert_align="c" align="l"/>
			<texture>ui_inGame2_edit_box_2</texture>
		</input>
	</backpack>
</w>
```

Note that the elements are initially drawn at a 1024x768 resolution, then stretched to fit the game resolution. This is why there are `_16` variants of these files, which are used when you play in a 16:9 resolution to compensate for this stretching effect. One application of this is to resize icons to appear square after stretching.

## Scripts

This is what makes everything work: how buttons respond to clicks, specify what elements are drawn on-screen, and modify the UI components on-the-fly.

Naturally, these are written in `.script` files with a class that inherits `CUIScriptWnd`. This class can then utilise the Layout defined above through a `CScriptXMLInit` class.

Example: See `item_backpack.script`