Data processing {#cha:processing}
===============

After scanning the object from all the desired angles and creating a
sufficient number of scans, you can proceed to building a 3D model. This
chapter offers a detailed description of the process. In most examples,
a plastic decorative figure of a duck will be used as the test object
().

![Target object: a duck<span
data-label="fig:duck"></span>](images/5_duck.png)

The process of creating the final model includes the following stages:

-   Revising and editing the data ();

-   Alignment of scans ();

-   Global data registration ();

-   Fusion of data into a single 3D model ();

-   Final editing of the 3D model ();

-   Texture mapping ().

Revising and editing scans {#sec:editing_scans}
--------------------------

Sequence of frames obtained at each scanning session is saved into a
separate scan. The list of all the scans in a given project is displayed
in of the application ().

Data in the are arranged in the following columns:

-   – scans marked with a in this column, will be displayed in the
    window and will be processed by all algorithms and tools
    of application.

-   – in this column, each scan has a colored square next to it. The
    filling of the square depends on the number of scan frames loaded
    into the application. When all the frames are loaded, the square
    will be fully filled in. When only key frames are loaded, it will
    be half-filled. When all the scan data is unloaded, it will be
    unfilled (see ). The scan color can be changed by pressing the
    corresponding square and selecting the desired color from
    the palette.

-   – ID number of the scan.

-   – when a scan is created, it will be automatically assigned a name
    like Scan1, Scan2 etc. based on values of and fields in the panel.
    To rename the scan, select it by left-clicking on its name. Then
    either press , or right-click on the scan’s name to open the
    drop-down menu and select the option. Both operations open a
    dialogue box where the new name can be entered.

-   – number of scan frames loaded into the memory (see ).

-   – total number of frames and the size of a particular scan.

-   – scan registration quality - which is the maximum value of the
    registration error for any frame in that scan.

### Data selection {#sub:data_selection}

#### Scan selection {#sub:scan_selection}

<span>| m<span>0.33</span>| m<span>0.3</span> | m<span>0.3</span>
|</span> **Purpose** & **Way** & **Alternative way**\
Just select scan in & Left-click on the scan name& —\
Enable displaying scan in window and activate it for processing by
algorithms & Left-click in the empty area of the leftmost column& Click
scan name with\
Disable displaying scan in window and deactivate it for processing by
algorithms & Left-click on icon & Click scan name with\
Batch selection (deselection) of scans for processing and displaying &
Click & Press ()\
Select a single scan for processing and deselect others & Click on the
scan name& Click in the empty area of the leftmost column\

In addition to the ways covered in the table above, you may use desired
commands from the drop-down menu of button. See also the full list of
the hotkeys given in .

Two types of scan selection are available in the application:

1.  By left-clicking on the scan name. This type of selection is used
    for drop-down menu commands. Clicking the icon on the panel will
    select all scans or clear all selections. This button also has a
    drop-down list that contains commands for selecting all scans, all
    fusions, inverting current selection, etc.

2.  By clicking in the empty area of the leftmost column in panel. The
    symbol appears next to the scans selected in this way. This type of
    selection is used for data representation in the window and
    operation of algorithms. Hitting shortcut will select all
    available scans. Clicking the scan name with or the leftmost cell
    with will select only this scan while clearing the other selections.
    Clicking the scan name with will invert the selection of this scan.

#### Frame selection {#ssub:surface_selection}

Double-clicking the scan name opens the panel, revealing all the frames
in that scan (). If the opened scan has only one frame, a panel with
frame data () will be shown instead of a list.

Highlighting specific frames will make them (and only them) appear in
the window. When the option is checked on the bottom, the selected
frames from other scans will also be displayed in the window. Frames can
be selected in the following ways:

-   Clicking on the frame name will select it while clearing
    other selections.

-   Clicking while holding the key allows selecting several frames
    at once.

-   Clicking while holding the key will select a sequence of frames
    within the specified range.

-   Clicking the icon on the panel selects all the frames or
    clears selection.

-   Using the dropbdown menu of the button you can quickly select all
    the key frames or all the textured frames.

-   Clicking will select all the frames.

By pressing the or shortcut you can start a sequential frame
demonstration, which can be stopped by pressing or by pressing again.

![Single-frame scan representation<span
data-label="fig:5_single_frame"></span>](images/5_single_frame.png)

### Scan revision {#sub:scan_revision}

As you begin building a 3D model, you should start by pre-processing
scans: remove unwanted frames, separate misaligned areas (if any) into
separate scans, cut out unwanted and non-rigid objects from the scene.

The following problems may be encountered:

-   misalignment of frames in relation to one another (see ) – this may
    occur due to small size, insufficient number or absence of
    geometrical features on the object or due to insufficient number of
    polygons in a frame.

-   misaligned parts (see ) – this occurs when the alignment algorithm
    working in real time incorrectly determined the position of the new
    frame relative to the previous ones.

-   unwanted objects are captured in the frame (see ).

A visual inspection of the frames can be very helpful in determining
problematic areas. To perform a visual inspection, select the scan and
view all the frames contained in it by holding or key on the keyboard.
Misaligned frames can easily be detected by means of this technique.

#### Removing unwanted frames {#ssub:surface_filtration}

You have to remove misaligned frames and frames with insufficient number
of polygons from the scans. To delete these frames, select them from the
list and press .

#### Scan separation {#ssub:scan_separation}

During the fine alignment process, frames within certain scans can be
misaligned. Sometimes it is possible to divide the problematic scan into
several parts, where each part is registered fairly well. In this case
divide the scan into several scans. Moving some of the frames into a new
scan requires the following steps:

![Moving some of the frames into a new scan<span
data-label="fig:5_move_scan"></span>](images/5_move_scan.png)

-   Select the frames you want to move in the panel.

-   In the panel click the and select ().

There is another way to fix alignment errors: you can reset current
values of frame transformations and repeat the registration, possibly
changing certain settings. To do so, select the desired scan in the
panel, click on it with and select from the drop-down menu. This will
reset the computed positions of individual frames within the scan. A
dialogue will appear prompting you to confirm the operation. To compute
new positions, you have to run the and algorithms (also
see \[sub:fine\_align\] section).

### Editing scans {#sub:scan_editing}

To edit the selected scans, open the tools from the side panel. , , , ,
and icons will appear alongside the existing icons on the icon bar of
the window, corresponding to the , , , , and tools. The latter is
covered in .

![ panel<span data-label="fig:5_editor"></span>](images/5_editor.png)

#### Moving, Rotating, Scaling (Transformation tool) {#ssub:move_rotate_scale}

is intended to move, rotate or scale objects in the window. To access
this tool, open the panel and select by either clicking button, or
pressing hotkey . The panel opens, displaying three tabs that correspond
to different modes of altering the object position in the global
coordinate system. The name of currently active mode is displayed at the
bottom of the window.

-   To enter the translation mode, click the tab or press the . Three
    input boxes containing the coordinates (in millimeters) of the
    current local coordinate system center will appear in the panel.
    Initial position of the local coordinate system is in the center of
    the global one. To translate the object, perform either of the
    following:

    -   Enter the new values of coordinates of local system into the
        input boxes of the panel. In order to adjust position only along
        a specific axis, press the corresponding button , or beforehand.

    -   Freely translate the object in the window by dragging the
        square control. Or translate the object along a specific axis by
        dragging only the necessary arrow control near the square
        control (see ).

-   To enter the rotation mode, click the tab or press the key. Three
    input boxes containing the values of Euler angles will appear in
    the panel. Initially all values are set equal to zero. To rotate the
    object, perform either of the following:

    -   Enter the new values of angles (in degrees) into the input boxes
        of the panel. In order to rotate the object only around a
        specific axis, press the corresponding button , or beforehand.

    -   Drag one of the three circles (see ).

-   To enter the scaling mode, click the tab or press the key. The
    single input box with the current scale (1.000) value will appear in
    the panel. To scale the object:

    -   Enter the new scale value in this input box.

    -   Drag the center of the control () or either of its round ends in
        the window.

After altering the object with any of the methods described above,
confirm or cancel your changes by clicking or , accordingly. Each time
you press the button, the object position is being saved in the project
history. Thus, the object position can be reverted to the initial one
using the button in the after you exit the panel.

#### Placing onto coordinate plane (Positioning tool) {#ssub:positioning}

You may need the model placed onto one of the coordinate planes for some
reasons (i.e. aesthetic grounds, preparing model for measurements,
screenshot capturing, exporting, etc.). Instead of adjusting the model
position by and modes in you can use special . To run it perform the
steps below:

![Positioning the model in the global coordinate system<span
data-label="fig:5_positioning"></span>](images/5_positioning.png)

1.  Open the panel on the side toolbar and press either or button in the
    upper part of window or hotkey .

2.  Choose the coordinate plane which you want the model to be placed
    onto by activating one of the following options: , or , or . Note
    that you may skip this step and return to it after
    step \[posit\_plane\_done\].

3.  Specify with at least three points on the surface, the plane
    automatically passes through their center of mass (). At that the
    following conditions are met: \[posit\_plane\_done\]

    1.  Specifying every additional point, you get the plane rebuilt.
        Any moment you can press and redefine points.

    2.  Not only plane passes through the center of mass of point set,
        but coordinate origin is shifted there.

    3.  This position of coordinate origin is not fixed and can be
        corrected, as described in step \[shift\_adjust\].

4.  You may also invert the direction of coordinate axis by pressing the
    corresponding button : for XOY plane, for YOZ plane, and for
    ZOX plane.

5.  You may additionally adjust the model’s position regarding the
    coordinate origin. Hold key and move the mouse with the following
    keys pressed: \[shift\_adjust\]

    1.  to rotate the model around the axis that is currently normal to
        the plane

    2.  to move the model along the plane in a fixed direction

    3.  to move freely along the plane

6.  Press to get the model fixed onto specified plane or if you do not
    satisfied with its position.

#### Smooth brush {#ssub:smoothing_brush}

The is a tool that can be used selectively in specific areas without
touching the areas, which do not require alteration (read about
automatic smoothing in the ).

To use the tool, select only one surface, open the panel and click the
icon or press hotkey . When the key is pressed, an orange spot will
appear around the cursor in the window. You can change its size either
by using the and shortcuts, or , or typing its size in millimeters in
the field, or adjusting the slider bar in the panel. Smooth strength can
also be set by typing its value in the field, or by adjusting the slider
bar. Pressing and holding the in this mode, will smooth the affected
areas (see ). Once done, click or buttons.

#### Erasing parts of scans

Nearly always, unwanted elements are captured during scanning, e.g.
operator’s hands, walls, surfaces that the object is located on, and
other irrelevant objects. This unwanted data can hinder post-processing.
In order to avoid this, it is recommended to get rid of them before
processing. There are several options designed for a quick and easy
removal of unwanted elements form the scene (see ).

-   is designed for deleting or areas or objects of medium size.

-   is useful for accurate cleaning of small areas of objects.

-   allows to select vast rectangular regions.

-   allows to create a selection by freely drawing it with the cursor.

-   is a special mode for removing flat surfaces (table, floor or base)
    that the object is located on. This mode uses a cutting plane that
    divides the scan into two parts: the first one is to be left and the
    second one is to be erased (see ).

![Eraser panel<span
data-label="fig:5_eraserpanel"></span>](images/5_eraserpanel.png)

The general procedure of erasing is as follows:

1.  In the panel select scan that needs editing and open the panel by
    clicking its icon on the side toolbar. Editor icons will appear
    alongside the existing ones on the icon bar of the window.

2.  If the scan is rendered with no texture, make sure it has a color
    different from red or any shade of red. Assigning non-red colors to
    scan will help you easily identify polygons selected for erasing. If
    necessary, change its color by clicking the colored square () near
    its name.

3.  Open tool by clicking on or by pressing hotkey .

4.  Select the desired erasing mode (consult the list above).

5.  Mark the elements to be erased. Press and hold down key and do
    either of following depending on the active mode.
    \[lst:eraser\_mark\]

    2D/3D selection:

    :   Adjust tool size (see table) and paint over the area of interest
        with .

    Rectangular selection:

    :   Drag the cursor to select a rectangular region.

    Lasso selection:

    :   Drag the cursor to freely outline an irregular region.

    Cutoff plane selection:

    :   Adjust tool size (see the table) and paint over the flat area.
        Once you have released the mouse button, a plane appears (). If
        necessary, adjust the level of the plane by using while holding
        down shortcut.

<span>| m<span>0.35</span>| m<span>0.55</span>|</span> **Purpose** &
**Way**\
Deselect region & Reselect this region while holding down\
Undo operation & Press or click\
Adjust size of the tool & Use and keys or while holding down\
Protect backface from erasing & Use toggle: — backface is protected (),
mandatory for — backface is affected ()\
 hardly accessible regions & Select (in the same way as for erasing) and
click to hide obstructing polygons\

6.  Click button to erase highlighted in red area or apply
    cutting plane.

#### Hiding polygons in Eraser tool

If some polygons obstruct the region that you want to erase, you can
hide them. Before step No. \[lst:eraser\_mark\] in the list in the
paragraph, do the following:

1.  Make sure the toggle is in position in window.

2.  Mark the obstructive region using the technique covered in
    step No. \[lst:eraser\_mark\].

3.  Click to get an access to the obstructed region.

4.  Now you can mark the region that needs to be erased.

Often, unwanted objects are captured during scanning, like operator’s
hands, walls, the surface on which the object is set, other irrelevant
objects. This unwanted data can hinder post-processing. To avoid this,
the application offers an option for quick and easy removal of unwanted
elements or objects from the scene.

![Eraser panel<span
data-label="fig:5_eraserpanel"></span>](images/5_eraserpanel.png)

Select the scan that needs editing and open the panel on the side
toolbar with the . Editing icons will appear alongside existing icons on
the icon bar of the window.

Select tool by clicking on or by pressing hotkey .

While in Eraser tool, you will be given several different ways to select
and delete the unwanted objects: 2D selection (default), 3D selection,
Rectangular selection and Cutoff plane selection. To choose the
selection mode, select the corresponding radio button. To select an
object(s) you wish to remove, press and hold . This will change your
cursor according to the active selection mode. Move your mouse cursor to
the object or the area you want to erase. Still holding , press and hold
to paint over this object/area. Selected polygons will become red
indicating the geometry to be erased.

To erase selected objects, click button. Keep in mind that you can
always undo the Erase operation by pressing or by clicking button in the
panel.

There are several ways to select an object or area that need to be
removed:

-   . This selection mode is easy to use and more suitable for deleting
    medium size objects or areas. The eraser is rendered as a circle
    which can select polygons of underlying objects (see ). Press and
    hold button to activate the eraser, add to select polygons. You can
    increase or decrease eraser’s radius using keys and or .

-   are useful for accurate cleaning of small areas of objects. The
    eraser is rendered on the scan as an orange projection of a sphere.
    It is easy to select 3D data precisely within the orange projection
    (see ). To operate eraser, use the same buttons as in mode.

-   . This selection mode is suitable for deleting large areas of
    objects as well as erasing flat surfaces like table, floor or wall.
    In this mode it is possible to select the specified rectangular area
    of the screen (see ). Press and hold , then drag the mouse cursor
    and you will see a rectangle that will change size according to the
    moves of your mouse. For area deselection use the key combination
    mentioned above.

-   . This

-   is an additional mode for removing some parts of the scans, such as
    floor, desk or base, in a word, flat things on which object
    was scanned. This mode utilizes a cutting plane dividing the scan
    into two parts: the first one to be left and the second one to be
    erased (see ). Below is the procedure for erasing in this mode:

    1.  Make sure that toggle is turned off .

    2.  Press and use and keys or to adjust circle size with respect to
        the size of scan’s flat region to be indicated to. Cursor view
        is similar to those one shown in .

    3.  Using , indicate flat region as a starting point for
        cutting plane. Multiple regions can be marked.

    4.  Once you have clicked, a plane appears in window. If necessary,
        adjust the level of plane. Press and hold key combination and
        spin back or forward to this end.

    5.  One side of the plane is red, the other is green (). Part of the
        scan laying under the red side is to be erased. Click to cut off
        this part or if the current selection does not suit you.

#### Defeature brush {#ssub:defeature}

Erasing some geometrical imperfections often demands further processing
of holes formed. combines functions of and tools and may significantly
boost your productivity. To use it follow the steps:

![Defeature brush panel<span
data-label="fig:5_defbrushpanel"></span>](images/5_defbrushpanel.png)

1.  Select the surface in panel. Only one model or one frame of scan are
    allowed to be chosen.

2.  Open the panel on the side toolbar and press either or button in the
    upper part of window or hotkey .

3.  In the panel choose selection type: or . Operational principle is
    the same as in tool, i.e. in 2D mode all the surfaces through the
    model are affected (if toggle is enabled), while in 3D the brush
    works over the visible surface. \[deforder\_2o3\]

    \

4.  Press to activate the tool. Depending on the selection type, a red
    circle or an orange spot will appear in window. \[deforder\_ctr\]

5.  Still holding , adjust spot size () or circle diameter () with or
    and buttons. Their size should match the size of feature
    being removed.

6.  Still holding , press and hold and paint over the area to
    be modified. A red stroke will appear on it. As you release the ,
    the feature will be deleted, the hole will be closed up, and the
    surface will be smoothed. \[deforder\_don\]

7.  Repeat, if necessary, steps \[deforder\_2o3\] – \[deforder\_don\].

8.  Press button, and all changes will be saved.

Scan alignment {#sec:scan_align}
--------------

Immediately after scanning, the application may not contain enough
information about the relative position of multiple scans. To combine
all scans into a single model, the data must be converted into a single
coordinate system, i.e. registration must be performed. The first stage
of performing this task is the semi-automatic alignment of scans using
the tool.

#### How to select scans and run alignment {#ssub:select_scans_toalign}

In the panel mark with the flag all the scans you intend to work with.
Click the button in the side panel. Marked scans listed in the same
order as in the panel appear in the left panel. During the tool
operation, the selected scans are divided into two sets: set of aligned
(registered) scans and non-aligned scans. The first set at the beginning
contains only one scan (the first one in the list) which is highlighted
in blue color, and its name is shown in bold and marked by the same
color icon .

The operator’s task is to align all scans to the already registered ones
and “assemble a model”. In general, the procedure includes the following
steps:

1.  Click the required tab in the panel.

2.  Select one scan from the unregistered group in the panel. The name
    of unregistered scan is displayed in a regular typeface. When
    selected, unregistered scan is marked by the green icon . Several
    scans can be selected by holding the .

3.  If necessary, specify point pairs, or sets onto the scans and click
    the desired alignment command button. The command affects all scans,
    marked by the round color icon in the .

Since each mode has variations in detail, see detailed information in
the corresponding subsections. Note that you can use either one or a
series of modes (see The Comparison table in the ): drag alignment,
rigid alignment with and without points specifying, automatic rigid
alignment and alignment with surface deformations.

#### How to change scan status {#ssub:regunreg_scans}

If several scans have been already aligned, they should be moved in the
registered set. Select them in the panel by using the , then click the
on the name of any scan, and select the option from the drop-down menu
or just double-click it in the list. From now on, the registered scans
are treated as one and cannot be moved independently of each other. In
order to change the status of a single scan, you can also double-click
the scan name in the list.

If some scan was marked as aligned by mistake, remove it from the
registered group by selecting the item from the drop-down menu or just
double-click it.

#### Displaying scans in  {#ssub:scans_in_3dview}

Scans selected in the panel are displayed in the window. Keys , and
switch between models shown in the window:

-   – shows only the blue models (aligned scans);

-   – shows only green models (scans currently under alignment);

-   – shows both sets of models.

Navigation in align mode is similar to navigation in the window:

-   Rotate – hold + move mouse;

-   Zoom in/out – use the or hold + move mouse;

-   Move model – move mouse while simultaneously holding and or the
    middle button.

### Drag alignment {#sub:drag_align}

Drag alignment is always available, irrespectively of which tab of the
panel is active. This alignment mode allows to align scans by manual
dragging them in window. Due to low accuracy of such dragging, this mode
can (optionally) be used for preliminary alignment before running more
accurate modes.

1.  Select scan for alignment, considering the recommendation stated in
    the beginning of the section . It is allowed to select multiple
    scans, but note that these scans will be aligned with registered
    scans as a single unit.

2.  Holding the key and one of the mouse buttons, move and rotate scan
    being aligned (a green one ) relative to the registered scan (a blue
    one ) to close proximity. The list of movements allowed and
    corresponding buttons is presented in the beginning of the .

3.  To confirm the alignment, release mouse buttons, the key and click
    the button. It is important to note, that scans being registered
    will not be added to the registered set (see ). It can be manually
    made by considering the recommendations in the beginning of
    the \[sec:scan\_align\].

4.  If you have several scans to align, repeat these steps for each of
    them sequentially.

### Automatic rigid alignment {#sub:autoalign}

Rigid alignment is a universal mode which is suitable for alignment most
of the scans. The easiest way to align scans is through the use of
auto-alignment. The advantages of the mode include the ability to align
several scans at once and to skip point specifying, while disadvantages
are as follows: requirements to the texture quality and to the size of
an overlapping area between scans being aligned.

To run the auto-alignment follow these steps:

1.  Make sure that tab is selected (see ).

2.  Select all the scans by using the key, as mentioned in the beginning
    of the .

3.  Click .

### Manual rigid alignment without points specifying {#sub:rigid_nopoint_align}

Rigid alignment can be carried out with and without points specifying.
If scans is in the state of close proximity (e.g. after “drag”
alignment) or if they have large overlapping area or rich texture, you
can skip points specifying when aligning the scans.

Perform the following steps:

1.  Make sure that tab is selected (see ).

2.  Select scan to be aligned, as mentioned in the beginning of the .

3.  Click the button. The alignment result is expected to be as pictured
    in the . If you are not satisfied with this result, click the and
    follow the recommendations given in the . \[list:alignmesh\]

4.  Select another scan from the list of unregistered scans and repeat
    the procedure above.

5.  Click to confirm your alignment results or to reject them.
    \[list:alignmesh\_done\]

#### Texture alignment {#ssub:texture_align}

If the object was scanned with texture, the texture alignment feature
may be used to ease the alignment of scans. Texture alignment uses
features from texture images of scanned objects and greatly decreases
the possibility of scans not to be aligned incorrectly. It also helps to
align objects with poor geometry, like round or flat objects with no
corners or geometrical features. However, if an object has rich and non
repetitive geometry, it is recommended to disable texture alignment to
decrease time needed for alignment algorithm. Please also keep in mind
that texture alignment will not be useful if texture of the object is
monochrome. To enable texture alignment, select the checkbox at the
bottom of the panel just before the step No. \[list:alignmesh\] in
procedure above.

![Checkbox for texture alignment<span
data-label="fig:5_texture_align"></span>](images/5_texture_align.png)

### Understanding specifying points and editing their position {#sub:points_howto}

Before considering the alignment with points, it is wise to stop at
highlighting matter of point pairs specifying. Alignment algorithm use
point pairs, or point sets in the “Constrained alignment” (), for
detecting areas on the scans to be brought close together.

For point alignment, mark several pairs of corresponding points on the
scans that have been aligned and scans being aligned. In the
“Constrained” mode point sets can be specified even within one or within
several scans being aligned, while in the rest of modes it is advisable
to confine the number of scans to one. Make sure that points for a given
pair correspond to the same point on the surface of a real object, but
note that high matching accuracy is not needed, since pairs are used
only for rough approximation before precise registration.

When specifying points in the “Rigid” and “Non-rigid” modes, pairs are
automatically created. Having specified one pair, you can immediately
create the next one. In the “Constrained” mode you have to confirm set
creation by pressing the button or by clicking the button on the left
panel, due to multiple points forming the set (see  and ).

You can toggle between the point pairs (sets) by pressing the and keys
or by clicking the in the window and selecting the relevant options from
the menu. You can relocate points of the pair (set). Hover with mouse
cursor over the point until the pair (set) will have been highlighted
with white color, then drag the point to the proper position with or
select the pair (set) and specify new position for the point by using
the . To confirm actions and deselect pair (set), press . You can also
remove either a pair (set) or one of its point. Click with on the point
and choose the required command from the menu. You can alternatively use
the button for removing the selected pair (set).

### Manual rigid alignment with points specifying {#sub:point_align}

It is advisable to use this mode when scans are located at a significant
distance from each other.

Follow the steps:

1.  Make sure that tab is selected (see ).

2.  Select scan to be aligned, as mentioned in the beginning of the .

3.  Specify several point pairs (), considering the recommendations
    given in the .

4.  Press the . This mode takes into account only coordinates of
    specified points and tries to reduce the distance between the
    markers from each pair.

5.  Carry out the steps \[list:alignmesh\]-\[list:alignmesh\_done\] of
    the procedure given in the .

### Non-rigid alignment {#sub:non_rigid_align}

While rigid alignment is only capable of performing such transformations
as translation and rotation, the non-rigid algorithm can deform 3D data.
This algorithm is intended to process so-called non-rigid objects,
i.e. objects that have changed their shape during scanning (e.g. models
of humans () or animals). Keep in mind that the surface obtained as a
result of deformation may differ from the surface of the actual object.

To run the non-rigid alignment, follow these steps:

1.  Make sure that tab is selected (see ).

2.  Select model(s) to be aligned, as mentioned in the beginning of
    the .

3.  If the models significantly differ from each other, it is advisable
    to specify some point pairs, considering the recommendations given
    in the .

4.  If necessary, adjust the deformation degree with slider. The greater
    the values, the more deformation, and the longer the
    computation lasts.

5.  Click the button. The algorithm will align models deforming their
    surfaces (). If you are not satisfied with the alignment results,
    press the and specify additional point pairs or reconsider location
    of the current pairs.

6.  Select another model form the unregistered set and repeat the
    steps above.

7.  Click to confirm your alignment results or to reject them.

### Constrained alignment {#sub:constr_align}

Constrained alignment allows to align not only scan to scan, but surface
to surface within one scan (see comparison of the modes in the ). In
comparison with other modes this one supports defining multi-point sets,
i.e. you can link up more than two points. This mode is useful when
aligning scans obtained during circular movements of the 3D scanner in
case the fine registration with enabled option failed to align them. To
run the constrained alignment, perform the following steps:

1.  Make sure that tab is selected (see ).

2.  Select the scan (scans) to be aligned, as mentioned in the beginning
    of the . This mode allows to work even with one registered () scan.

3.  Specify one or several point sets on the scan surface (),
    considering the recommendations given in the .

4.  Click the button to run alignment with constraints (results are
    shown in ). If you are not satisfied with the alignment results,
    press the and specify additional point sets or reconsider location
    of the current sets. To repeat the undone operation, click (Redo).

5.  Click to confirm your alignment results or to reject them.

Global registration {#sec:global_optimization}
-------------------

Once alignment of all scans is complete, proceed to the next stage –
global registration. The global registration algorithm converts all
one-frame surfaces into a single coordinate system using information on
the mutual position of each pair of surfaces. To do it, a set of special
geometry points is selected on each of the frames followed by a search
for pair matches between the points on different frames. For the
algorithm to perform correctly, initial approximation is required which
is performed in the process of using the tool.

To launch the algorithm, select all aligned scans in the panel. Open the
panel. Locate the section and click the button.

### Global registration parameters {#sub:global_parameters}

-   – the type of algorithm to be used for registration of scans. If
    object has rich texture and poor geometry, consider
    selecting option. For objects with rich geometry it is possible to
    set mode in order to increase registration speed.

-   – the minimum distance between adjoining feature points on the
    object in millimeters.

-   – the number of iterations of global optimization algorithm [^1].

-   – the threshold of allowable misalignment of key frames, in fact,
    the distance between surfaces being registered. If you scanned with
    from a long distance (), you must change the default value to 5.

### Possible global registration errors {#sub:global_optimization_defects}

-   After the Global Registration algorithm has finished, the frames are
    in disarray (see ) or the position of frames has not changed. This
    is due to the fact that the application is configured for a
    different scanner type than the one that was used to capture data.
    Change the device type in settings (see ).

-   The algorithm has completed successfully, but there is a gap between
    two or more scans (see ) – select just these scans in the and run
    the global registration algorithm for them. If the scans have drawn
    closer to each other but have not aligned after algorithm
    completion, increase the number of iterations and rerun
    the algorithm. Repeat it until full alignment is reached. Then run
    global registration for all data once again. If there are several
    problematic scans and you are unable to align them, try aligning
    just two of them. Then gradually increase the number of scans until
    all scans become aligned.

Outlier removal {#sec:outlier_removal}
---------------

During the scanning, so called outliers may appear on the scene.
Outliers are small surfaces not connected to the main surfaces. These
small surfaces are subject to removal, because they may spoil the model
or produce unwanted fragments. There are two ways to do it: erase them
before fusion (preventive approach) and after fusion (so called
furthering approach, see ). Preventive approach is advisable, because it
decreases the possibility to spoil fusion with attached noisy features.

This approach is based on the statistical algorithm which calculates for
every surface point the mean distances from it to a certain number of
their neighboring points and their standard deviation. Then all points
whose mean distances are outside an interval defined by the global
distances mean for all points and standard deviation are considered as
outliers and removed from the scene.

For better results, before starting algorithm, it is recommended to run
global registration. If you have not run it and have started , a dialog
box appears prompting you to run global registration.

In most of the cases none of the parameters accessed through button
needs editing. But if necessary, parameters’ values can be adjusted:

-   – is a standard deviation multiplier. The values of this parameter
    should be chosen according to the following recommendations:

    -   2 – for quite noisy surfaces;

    -   3 – for less noisy surfaces.

-   – should be set equal to the of expected to be run later.

Press to run .

Fusion {#sec:fusion}
------

Fusion is a process of creation a polygonal 3D model. It can be
described as melting and solidifying the frames obtained and processed.
This is the most interesting part of the processing because polygonal 3D
model is what exactly people wait from 3D scanning. To this end, you can
use one of the following algorithms having self-explanatory names (see
also the summary given in the ):

-   produces quick results.

-   is good for human body scanning due to its ability to compensate
    slight movements of the person being scanned.

-   perfectly reconstructs fine features and is suited both for
    industrial objects and human bodies. It is the only mode that
    unveils all capabilities of scanner.

<span>|m<span>0.1</span>|| m<span>0.27</span>| m<span>0.27</span>|
m<span>0.27</span>|</span> & **Fast Fusion** & **Smooth Fusion** &
**Sharp Fusion**\
Usage & Fast results for large datasets, for measurements & Large, noisy
datasets with patchy missing regions, scans of stirring objects & Scans
from , any scans with regions with fine details and sharp edges\
&\
&\
&\
 option & N/A &\
Features & Relatively noisy resulting surfaces. Mode has an additional
parameter . & Smoother results. Mode can compensate slight movements,
but it is not recommended for accurate measurements. It is also
relatively slow. & Higher level of detail. Faster than Smooth Fusion.
But it can intensify the existing noise.\

\[tbl:fusion\]

To obtain a model:

1.  Make sure the scans you are going to fuse have passed .

2.  Select with button scan or scans in the panel.

3.  Enter the panel.

4.  Select the necessary mode, optionally specify values in
    the parameters.

5.  Click .

6.  Once algorithm completes calculations, the model appears in the
    window and in the panel, its name matching the algorithm name.

The following parameters are used in the fusion algorithms:

-   (millimeters) is the step of the grid which is used to reconstruct a
    polygonal model. In other words this parameter defines the minimal
    space unit where the polygon of the model will be build in. The
    lower values, the sharper the shape. When specifying values, you
    should take into the consideration default values and lower limits
    given in the .

-   (only for Fast fusion) (multiplier, integer) is a factor which
    defines surrounding space that algorithm takes into consideration
    when adding each new minimal space unit. Note that the size of the
    space unit remains unchanged and equals to the value, while the
    actual search radius is the product of by .

-   (not available for Fast fusion) settles the algorithm to fill holes
    in the mesh being reconstructed. The ways the holes will be filled
    in are as follows:

    -   – all holes having radius no greater than the specified in the
        textbox value (millimeters) will be filled in;

    -   automatically fills in all holes in the mesh;

    -   option prompt you to fill in holes manually in the automatically
        open panel.

-   (not available for Fast fusion) – the option (can assume either
    or value) allows to erase small embossings from the surface, where
    targets were stuck on (see ).

Upon successful global registration, all the processed data can be fused
into a single polygonal 3D model. To start the Fusion algorithm, open
the panel and run either , or button. Each algorithm will produce a
polygonal 3D model for which a new scan will be created in the project.
By default, scans with models created by the fusion algorithm have names
like , etc. or , , etc. depending on what algorithm was used.

Though all Fusion algorithms produce fused mesh, there are some
differences:

-   is the fastest algorithm, consumes relatively small amount of memory
    and is capable of working with large datasets; may produce
    noisy results. It requires models to be post-processed afterwards.

-   is not that fast and may require significant amount of time and
    memory to produce the result; the result is usually smoother, less
    noisy and, thus, requires less time for post-processing; produces
    mesh which is close by level of detail to the one obtained by the
    with the value twice that is capable of creating watertight meshes
    filling up all the holes in the data; is very useful for fusing
    noisy, partially absent data. is perfectly suited for creation of
    human body models, shows good results of shape reconstruction
    (esp. shape of head).

-   is particularly suitable for reconstruction of fine details and
    sharp edges of the model; the detailing of the result is usually
    higher than in case of or ; may exaggerate noise when working with
    too noisy data; is capable of creating watertight meshes filling up
    all the holes in the data; is faster than algorithm.

If you forgot to run the global registration (see ) before fusing the 3D
model, the application will open a pop-up reminder with a prompt to
perform the skipped procedure ().

![Dialog for starting the Global Registration algorithm<span
data-label="fig:5_confirmation"></span>](images/5_confirmation.png)

The algorithm has several configurable parameters:

-   – the size of the triangulation grid step in millimeters. For
    different scanners its value should be set according to the
    following rules:

    -   for **S**-type and scanners the recommended value is 0.3, but no
        less than 0.1;

    -   for **M**-type scanners the recommended value is 1, but no less
        than 0.4;

    -   for **L**-type scanners the recommended value is 1-2, but no
        less than 0.5.

-   – a factor for determining the size of the space area, which data
    will be used to set the position of each resulting model vertex.

The Smooth Fusion and Sharp Fusion algorithms have the following
parameters:

-   – is the same as above. In order to get sharper results for the ,
    you should set the resolution value twice less as you would do with
    Fast Fusion;

-   – can be set to either , which produce a mesh with all the holes
    filled in, either which creates a mesh with holes less than the
    specified radius filled or which opens panel prompting you to fill
    in holes manually after the model has been fused;

-   – the maximal radius of the hole to be filled in in millimeters;

-   – the option (can assume either or value) allows to erase small
    embossings from the surface, where targets were stuck on (see ).

The comparison of results from the same source data processed with and
is shown on the .

### Possible fusion algorithm errors {#sub:fusion_errors}

Sometimes various defects appear on the resulting 3D model after fusion,
some of them can be corrected by creating additional scans, while others
can be corrected by using model processing tools described in the next
section.

Errors which can be corrected by capturing additional scans include
low-amplitude noise on the surface (see ). Normally this indicates that
the affected area has a small number of frames. The number of frames
needed to eliminate this noise depends on the reflective properties of
the object’s surface. To correct the error, one more scan is necessary
to cover the noisy area (see ).

Sometimes the reason for the noise is insufficient number of scanning
angles. Areas captured at a larger angle turn out to have more noise
than areas captured at the direct angle (i.e. 90 degrees). This can be
corrected by scanning the area again using the required angle.

When scanning conditions or the object’s features are such that no
additional data can be captured, the errors can be corrected using tools
() or (). If such errors are frequent, reduce the speed at which the
scanner is moving around the object while scanning, or increase the
capture rate (see ).

Model editing {#sec:3d_model_editing}
-------------

The resulting fusion model may contain surface defects due to scanning
or registration errors. A number of tools exist in the application for
correcting such errors:

-   the tool is used for correcting the model’s triangulation errors.

-   the is used for filtering and deleting small objects near the
    surface of the model.

-   the tool is used for filling holes and smoothing out the model’s
    edges semi-automatically.

-   the algorithm is used for filling the model’s holes automatically.

-   the algorithm is used for filtering low-amplitude noise over the
    whole model.

-   the tool is used for smoothing surface areas with the most
    noise manually.

-   the algorithm is used to reduce the number of polygons within a
    model while minimizing the loss of accuracy.

-   the algorithm is used to create isotropic mesh while keeping the
    processed mesh as close to the original as possible.

Each of these algorithms processes all the scans selected in panel and
replaces the original data with the results. If the algorithm has not
been successful, the original data can be restored by pressing button in
Panel.

### Correcting triangulation errors {#sub:repair}

After the operation of some algorithms, the resulting model may contain
triangulation errors. They include:

-   - points which are not vertices of any of the triangles.

-   .

-   – triangles pointing to non-existent vertices.

-   – triangles with at least two of the three vertices coincide.

-   – faces with a fully coinciding sets of vertices.

-   – edges adjacent to the three or more faces.

-   – faces with normals directed opposite of the normals of the
    adjoining faces.

To correct these errors, select a model in , and press on a side panel.
If no triangulation errors are detected by the algorithm, the
application will notify the user that no defects have been found.
Otherwise, the panel will open, displaying the above mentioned list of
defects to be corrected. Next to the names of the defects, a column will
appear stating the number of defects of a certain type found in the
model. You can select all defects by pressing . This will display all
the defective vertices and triangles on the model using colored points.
You can disable displaying defects of any type by unmarking the icon
next to their names, or disable displaying all defects by pressing . To
correct the defects, press . Press button to accept the changes.

### Filter for small objects {#sub:outliers_filtering}

If you had not erased outliers before fusion (see ), they might be
solidified and preserved on the scene as small distant pieces. Outliers
on the fusion can be removed effectively using a filtering algorithm.

To do so, select only the model you are editing in the and open the
panel. Click the button next to to run the filtration algorithm (see ).
The algorithm settings window will be open after pressing the button.
The following algorithm parameters are available:

-   – selecting the option from the drop-down menu, will erase all
    objects except the one consisting of the most polygons; selecting
    the option will erase all scene objects with the number of polygons
    less than specified in the parameter.

-   – threshold parameter, number of polygons, that is used in case the
    filter mode is set to .

### Hole filling and edge smoothing {#sub:hole_filling}

Sometimes the complex shape of an object or scanning conditions do not
allow for proper capturing of all its parts. As a result, the fused 3D
model will have holes. In those instances, the hole filling tool can be
used for interpolating the surface.

To start analyzing and correcting the model, select it and press the
button on the side panel. This panel has two tabs: and , each of them
containing a list of holes detected on the surface which are sorted by
their perimeter length. When a hole is selected, the corresponding edge
will be highlighted in the window. If the option is checked, the model
will automatically turn to display the selected edge in the window. By
default, the camera moves smoothly from one edge to another when
switching between edges. If the model itself is large, this movement may
take too long. To expedite the switching, clear the check box.

The user must select edges for correction by checking the checkbox next
to them. Such edges will be highlighted in red in the window (). The and
buttons on the panel allow making a selection / clearing all selections.
You can also select edges right on the model. To do this, rotate the
model to make the edge visible in the window. Then press the to select
it.

Under the Tab, you can run automatic smoothing of the holes after their
filling by checking the option (see also ). Under the Tab, use the
slider to control the intensity of edge smoothing. Also, you can use
this tab to smooth out a part of the edge instead of the whole one. To
do this, rotate the model to make the edge visible and mark it in the
list as “processing required”. Then hold the and move the mouse over the
edge to drag apart the ends of the profile to the desired position ().

After all the edges to be fixed have been selected, click or buttons.
The model will be fixed. If the result is satisfactory, press to confirm
the operation. Otherwise, you can always use the button to cancel
changes. If you try to exit the mode without accepting changes, the
program will ask you to confirm the action.

### Automatic hole filling {#sub:auto_fiull}

For quick, automatic hole filling, use the algorithm in the panel. The
algorithm uses the same edges as the tool, processing only holes with
the parameters corresponding to the only setting, accessed through
button (see ):

-   – maximum length of the hole perimeter in millimeters. Holes with
    parameters not exceeding the specified limit will be processed.

### Smoothing {#sub:auto_smoothing}

The smoothing algorithm is used for smoothing noisy areas of the 3D
model. Two tools exist in the application: automatic smoothing of the
whole model and manual smoothing of specific areas with a brush (see ).

To run the automatic smoothing, open the panel and select the operation.
There is only one parameter to set:

-   – specifies the number of smoothing algorithm iterations to
    be performed.

### Mesh simplification {#sub:mesh_optimization}

The mesh produced after fusion may not be optimal for some applications
because it will contain a large number of polygons. This complexity will
increase the amount of memory the model occupies, hindering further
processing. To optimize the model size and retain accuracy, use the
mesh-simplification algorithm.

![Original mesh shown on the left, optimized mesh on the right.<span
data-label="fig:5_mesh_optimization"></span>](images/5_mesh_optimization.png)

Select the model and open the panel. Two algorithms are available.

#### Conventional algorithm {#ssub:conv_mesh_simp}

Open the drop-down algorithm settings by clicking the button next to .
Select the appropriate processing method (determined by the value):

-   – optimize model to a predetermined accuracy:

    -   The parameter defines the optimized model’s maximum allowable
        deviation (in millimeters) from the original one. When the
        algorithm reaches this value, the optimization stops.

-   – perform simple mesh optimization, removing triangles with edges
    whose lengths are less than the value (in millimeters).

-   – simplify the model by targeting the number of triangles specified
    in the parameter. The algorithm minimizes the resulting model’s
    deviation from the original model, but the final deviation value is
    unknown until processing concludes. Use this method when you know
    how many triangles the resulting model should include.

-   – similar to the algorithm but intended for meshes with textures
    mapped by the method (see ). This approach not only simplifies the
    polygon grid, reducing the number of triangles, but it
    preserves texture.

-   – simplify a textured model by targeting the number of vertices
    specified in the parameter.

The three first algorithms in the list above have additional parameters:

-   – maintain the model boundary. Mesh simplification on the scan edges
    may affect their geometry. Thus, if the shape of the boundaries is
    more important than the optimized mesh, select the value. Otherwise,
    select , and the algorithm will simplify the boundary mesh.

-   – the angle between two neighboring faces normals. You can specify
    an angle (120$\textdegree$ default) to prevent from creating
    degenerate triangles. If the angle measure in some region exceeds
    the specified value, the algorithm will not simplify the mesh in
    this region. Note that the default value is appropriate in
    most circumstances.

After adjusting the algorithm settings, press to start processing.

#### Fast mesh simplification {#ssub:fast_mesh_simp}

algorithm works faster than conventional one. To start it, perform these
steps:

1.  Open the drop-down algorithm settings by clicking button next to
    the name.

2.  Specify in the textbox the desired number of triangles in the
    resulting model. You can find out number of triangles in the actual
    model by double-clicking it in the .

3.  Set option:

    -   If this option is set to , value specified in the textbox
        remains constant

    -   If this option is set to , value specified in the textbox can be
        automatically updated for the purpose of a better quality of the
        resulting surface.

4.  Click to run the algorithm.

<span>| m<span>0.15</span>| m<span>0.35</span>|
m<span>0.45</span>|</span> **Quantitative** & **Qualitative** &
**Definition**\
 & & Distance between simplified and original surfaces\
 & & Deviation between normals in vertices of simplified and original
surfaces\
& & Maximal deviation between normals in vertices of simplified and
original surfaces максимальное отклонение нормалей в вершине после
упрошения относительно неупрощенной. чем меньше - тем лучше качество
упрощенной поверхности,\
& & ratio of x to y отношение длины самой длинной стороны упрощененого
треугольника к самой короткой стороне. чем меньше - тем лучше качество
упрощенной поверхности\
& & после упрощения углы между нормалями соседних треугольников не
должны превышать указанное значение.\
The greater value, the better qulaity&The smaller values, the better
quality& —\

Automatic Processing {#sec:automatic_processing}
--------------------

Automatic Processing is a special mode of panel intended to save time
and simplify post processing. It allows to run all post-processing
algorithms from panel (Rough, Fine and Global Registration, Fast, Smooth
and Sharp Fusion, Small Objects Filter or Outlier Removal, Hole Filling,
Mesh Simplification, Remesh and Smoothing) with a press of only one
button.

![The extended menu<span
data-label="fig:5_Auto_Process"></span>](images/5_Auto_Post_Processing_alternative.png)

To switch from Manual to Automatic mode, open panel and choose option in
the dropdown list located in left corner of the section. Press button
near the to view all options available in Automatic Mode. Note that only
Global Registration, Fast Fusion and Small Objects Filter are enabled by
default. In order to perform other actions automatically, choose the
option in the dropdown list next to the required function or the option
to exclude a function from Automatic Processing. Click button or press
hot key combination to start the Automatic Processing.

All settings and parameters of algorithms are taken from the the Manual
mode page. To change settings of algorithms, switch to mode, change
settings and run the Automatic Processing – all changes will be applied.

Keep in mind that all algorithms are performed in the same order as they
are listed – starting from Rough Serial Registration and ending with
Remesh. This means that if you want to run Small Objects Filter before
Fast Fusion or Global Registration, you have to do it manually.

Unlike Manual processing, Automatic processing does not require constant
attention of the user, so it is more convenient when processing large
objects – you can configure the settings, start the processing and leave
it for some time. It can also be successfully used for processing of
objects of any size, reducing the number of mouse clicks to get the
result.

Texturing {#sec:texturize}
---------

Artec scanners are equipped with color camera, allowing you to capture
3D surfaces with texture and expanding the range of objects available
for scanning. Perform the following steps:

1.  Make sure the checkbox is cleared.

2.  If necessary, adjust the frequency of capturing texture
    frames (see ).

3.  It is advisable not to turn off the flash bulb.

4.  In the mode adjust the texture brightness by using the same name
    slier in the panel.

5.  Scan the object with any tracker. Captured frames are marked with
    the “T” letter in the surface view window ().

6.  Process the data and create a model, consulting the list in the
    beginning of the .

7.  Run a mesh simplification algorithm for the model obtained (see ).
    This makes the texturing faster.

8.  Use the panel to apply texture to the model.

Texture mapping is a process of projecting textures from the individual
frames to the fused mesh. Texture mapping assumes that the model was not
moved or deformed (i.e. stayed in the same position as the scans that it
was built from).

### Texture mapping {#sub:texture_mapping}

3D model obtained after alignment and optimization contains no texture
information. To map textures on a model, open panel and select the
fusion that you want to apply texture on in list box (see ). After
fusion is selected, select the scans that the fusion was built from (and
that thus have the required textures) in the second listbox.

![Simplified illustration of texture mapping: texture as a single
file<span data-label="fig:5_uv"></span>](images/5_uv.png)

![Choosing texture application method and adjusting its parameters<span
data-label="fig:5_texture"></span>](images/5_texture.png)

Next you will need to choose method for applying textures to the model.
Two methods are available:

-   ;

-   ;

The method rasterizes all mesh triangles into texture images,
individually duplicating UV coordinates for vertices and producing
non-continuos texture (or textures). Size of triangles[^2] (see ) can be
adjusted in pixels with the slider in the panel. The resulting texture
size can be selected from the drop-down list (maximum texture size
depends on the capabilities of the graphics card). After changing the
triangles/texture size, estimated number of textures will be displayed
in the zone at the bottom of the panel, but the actual number may
slightly differ.

The method cut the surface into pieces, unfold and nest them on the flat
and fit them into the image of specified size (see  and in ). This
method takes longer time than the triangle map method, but the texture
obtained is much more convenient for manual editing.

If you want to modify texture by utilizing inpainting tecniques, there
are two options to choose:

-   option allows to apply texture to the regions with no texture
    information by spreading it from the neighboring regions.

-   option does the same, painting out targets by applying surrounding
    texture to them (targets can be used to facilitate scanning ()).
    Selecting this checkbox makes sense if you activated the option when
    producing this fusion ().

There is one option called which is selected by default and aims to
compensate for uneven lighting caused by movement of a scanner flash
unit during scanning. It is not desirable to clear this checkbox.

Finally, select size of the texture and press to start texture mapping
process.

If you want to reduce or increase resolution () of the already mapped
texture, you can remap it times faster thanks to the option.

<span>| c || m<span>4cm</span> | c | m<span>2.3cm</span> |
m<span>4cm</span> |</span> **Mode** & **Texture distortion** & **Speed**
& **Number of textures** & **Texture resolution management**\
Triangles map & Does not keep aspect ratio of triangles & & 1 or more &
Through adjusting triangle size and texture image resolution\
Texture atlas & Keeps aspect ratio of triangles & – & & Through
adjusting texture image resolution\

It should be noted that all surfaces, except those needed for texturing,
are unloaded from RAM before mapping procedure. This is done in order to
optimize computer resources usage. For more detailed description of
project data selective loading into RAM see .

### Texture adjusting {#sub:adjust_texture}

After the texture mapping process is complete, you will be able to
adjust texture on the model ().

![Hue, saturation and brightness representation<span
data-label="fig:5_husatur"></span>](images/5_husatur.png)

The following parameters of the texture can be adjusted with the
corresponding sliders (see  for explanation):

![Texture adjustments<span
data-label="fig:5_texture_adjustments"></span>](images/5_texture_adjustments.png)

-   Brightness;

-   Saturation;

-   Hue;

-   Contrast;

-   Gamma correction.

Initial position of slider bar corresponds to the current color of the
texture. Dragging it to left or to right you bring out the color from
the color wheel in a clockwise direction or in a counterclockwise
direction.

After making the necessary changes, press button to transfer obtained
textured model into the panel.

Manual inpainting with Texture healing brush {#sec:healing_brush}
--------------------------------------------

You can manually inpaint missing texture by applying . This tool is
based on the same algorithm as the option covered in . Inpainting
algorithm uses texture from the neighboring regions to fill in the
regions with missing or incorrect texture. shows a small imperfection on
the texture: a felt-tip pen mark on the actual figurine. Results of
inpainting this region are given in .

To launch the tool and inpaint texture:

1.  Make sure the model that you are going to edit is marked with icon.

2.  Open panel by clicking its icon on the side toolbar.

3.  Select by clicking the icon.

4.  Select the desired mode: or .

5.  Press and hold down button while using or and keys to adjust the
    tool size. The tool size should not exceed the size of the region
    with texture that needs correction.

6.  Paint over the region of interest with while holding down button so
    that the tool (a circle or a spot) goes over problem area only. Try
    not to touch neighboring areas.

7.  Click to accept the changes or to revert them.

[^1]: Optimization is a part of the actual global registration algorithm

[^2]: Size of triangles is determined by the number of pixels per
    triangle side.
