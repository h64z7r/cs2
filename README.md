java c159.235 2023 S02 — Assignment 2
This assignment covers the topics: coordinates, transformations, 3d modelling, and visible
surfaces.
Wireframe Data Viewer
Write a Java program that renders a 3 dimensional triangle wireframe surface data model
and allows one to rotate and scale the model so that it can be viewed from any direction.
This could be thought of as a simple CAD program.
Your application needs to be set up so that the ffgures rotate as the sliders are adjusting,
they uniformly resize after clicking the appropriate button, and they get re-drawn when
toggling between anti-aliasing on/off.
Use the simple viewing model where the “eye” point is on the positive z-axis looking down
and the ffgures are drawn by orthographically projecting onto the xy-plane.
You will need to decide how to transform the vertex coordinates in the wireframe data for
the given rotations and scalings. You can then draw each triangle on the Graphics2D canvas
with the transformed vertex positions.
Your rendered wireframe ffgures should appear “solid”—the wireframe outlines should be
clearly visible. You need to implement some procedure to remove hidden surfaces. You
should at least implement the back face culling method. You should ffnd that this will
remove most hidden surfaces—but not all of them. Top marks will be earned by those
programs that are able to remove all hidden surfaces.
Sample triangle mesh wireframe data ffles are provided on Stream. You program should
work smoothly with all of them.
You do not need to implement the 2D viewport clipping procedures described in the lectures.
You can let the Java AWT handle all that.
You do not need to apply any lighting or shading to the surfaces—this will be dealt with
later on in the course.
Completing the assignment
A set of startup Java source ffles are on Stream that will function as skeleton code for
the assignment. Load these into a new IntelliJ project and start up Main.java—this is the
“controller” part of your project. This features a number of JPanels with slider and button
widgets. Familiarize yourself with the various components in the project folder.
To complete the assignment, provide implementations for the other components. When
doing so you will need to make small adjustments to Main.java—mostly in the event handler
method. Complete as follows:
1. The Wireframe.java ffle contains a class that holds all data for a given triangle mesh
ffgure. Decide what data needs to be stored there. Provide an implementation inWireframeDataIO.java to read from a wireframe .tri ffle and create a new instance of
Wireframe
[2 marks]2. Complete the implementation of the rotation matrix utilities in Transform3d.java. The
purpose of this utility is to be able to readily generate a full rotation matrix given
rotation angles in each of the 3 planes.
[2 marks]
3. Make appropriate modiffcation to the Wireframe class so that these rotations, as well
as scaling, can be applied to the triangle mesh data.
[3 marks]
4. Provide an implementation in WireframeDrawer.java to draw the triangles on a JPanel
using the transformed vertex positions. This needs to happen directly in response to
adjusting the sliders and clicking the buttons.
[3 marks]
5. Provide an implementation of back face culling. You will need to decide the appropriate
places in your project to make the modiffcations.
[4 marks]
6. Further modify your project to implement the Painter’s Algorithm. Here you will need
to decide on a suitable approach for deffning the “depth” of your triangles and how to
sort them.
[4 marks]
7. Implement the action following the anti-aliasing buttons, so that the lines will be
drawn with anti-aliasing either on or off. Decide how this will be actioned in the Main
controller. For this part is enough to use the anti-aliasing tools built-in with the Java
AWT.
[2 marks]
Due date: 2024 September 20, 11:55pm.
Please submit via the submission link on Stream.
Total 20 marks (20% of your ffnal grade).Coding hints
• To read and parse a text ffle (as in the wireframe data ffles), the JDK supplied
java.util.Scanner class is a useful utility. Create a Scanner object and use the .nextLine()
method to step through the ffle line-by-line. This method will give you a line in a ffle as
a String. Note: to use this utility, you will need to handle the FileNotFoundException.
• There are situations where you will need to split a String into sub-strings according to
some delimiter (e.g. space, tab, comma, . . .). Use the java.util.StringTokenizer for
this.
• To convert a String to a numeric value, use Integer.parseInt() or Double.parseDouble().
• It is suggested that you draw each triangle using something like:
// xDraw and yDraw are s i ze 3 arrays giving the t r iangle vertex positions
Polygon aTriangle = new Polygon(xDraw, yDraw, 3);
// . . . assign values to aTriangle . . .
// The implementation de tail s wil l depend upon how you have
// designed your program
g2.setColor(Color.gray);
g2.fill(aTriangle); // Colour in the t r iangle surface
g2.setColor(Color.black);
g2.draw(aTriangle); // Draw the t r iangle outline
Note that xDraw and yDraw are integer arrays.

         
加QQ：99515681  WX：codinghelp
