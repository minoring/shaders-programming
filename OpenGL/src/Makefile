CXX=g++
CC=g++
CXXFLAGS=-g -Wall -MMD -std=c++14
LDFLAGS=-lglfw -lGLEW -framework OpenGL
SOURCES=Application.cpp
OBJS=IndexBuffer.o VertexBuffer.o Renderer.o VertexArray.o Shader.o Texture.o vendor/stb_image/stb_image.o vendor/imgui/imgui_draw.o vendor/imgui/imgui_impl_glfw_gl3.o vendor/imgui/imgui.o vendor/imgui/imgui_demo.o tests/TestClearColor.o tests/Test.o tests/TestTexture2D.o
TARGET=app

all: $(TARGET)

$(TARGET): $(SOURCES) $(OBJS)
	$(CC) $(CXXFLAGS) $(SOURCES) $(OBJS) -o $@ $(LDFLAGS)

IndexBuffer.o: IndexBuffer.cpp IndexBuffer.h Renderer.o

VertexBuffer.o: VertexBuffer.cpp VertexBuffer.h Renderer.o

Shader.o: Shader.cpp Shader.h Renderer.o

VertexArray.o: VertexArray.h VertexArray.cpp VertexBufferLayout.h Renderer.o VertexBuffer.o

Renderer.o: Renderer.cpp Renderer.h

Texture.o: Texture.cpp Texture.h

stb_image.o: vendor/stb_image/stb_image.h vendor/stb_image/stb_image.cpp

imgui_draw.o: vendor/imgui/imgui_draw.cpp

imgui_impl_glfw_gl3.o: vendor/imgui/imgui_impl_glfw_gl3.cpp

imgui.o: vendor/imgui/imgui.cpp

imgui_demo.o: vendor/imgui/imgui_demo.cpp

TestClearColor.o: tests/TestClearColor.cpp tests/Test.h tests/TestClearColor.h

Test.o: tests/Test.cpp tests/Test.h

TestTexture2D.o : tests/TestTexture2D.cpp tests/TestTexture2D.h

clean:
	rm -f *.o
	rm -f *.d
	rm -rf *.gch
	rm -f $(TARGET)
