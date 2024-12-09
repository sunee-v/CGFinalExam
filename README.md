# CG Final Exam: Even

**Shaders Made**
-  Colour correction (LUT)
-  Scrolling Texture Shader
-  Vertex Displacement
-  Colour changing shader with texture

*Each shader was made using shadergraph*

**Colour Correction Shader:** I started off by creating a pink lut. This lut is used for a texture 2D. Now on shader graph, I added a screen position node and connected it to a URP sample buffer node. This is set to BlitzSource to get the image of the frame where it is currently at before it renders. After I lerped the frames before renders with the LUT image, which ends up correcting the colours as needed.
![LUTShadergraph](https://github.com/user-attachments/assets/93f31309-2c68-47ee-9104-c592581530f8)

**Scrolling Texture Shader:** I used a time node and outputed it into the offset node from the Tiling and Offset. From here, I just placed the texture I wanted to scroll and connected the input with the tiling and offset output. This returned a scrolling texture.

**Vertex Displacement Shader:** This shader is hard to see as it is applied to the mountains of the yoshi scene. It uses the position of the object in the world. This uses the x and z from the split node to add to time. This makes it so that the vertices move based on time. Then it is added to sine to make it a wave-like motion which is then calculated and added into the position node of the vertex shader.

**Colour changing shader with texture:** Uses a texture created on photoshop. Time is masked with multiply node along with a float to manage how fast it changes colour. After this, a sine node is added to create a wave-like flashing output. this is connected to the tiling and offset, which is connected to the texture to give the tiled texture look. I lerp between two colours, a dark green and lighter green, then multiply with the texture image to make it so that the texture along with the greens are changing over sine time.
