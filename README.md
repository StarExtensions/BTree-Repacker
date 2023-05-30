# BTree Repacker

This is a small tool that writes all the data in a Starbound BTreeDB5 file (worlds, shipworlds, universe chunks) to a new file.
This allows you to debloat your files when they get too big, since BTreeDB5 files tend to waste a lot of space over time.

**A prebuilt 64-bit Windows binary is provided - see releases.**

To compile it you must have a copy of the Starbound 1.4.4 source code, which will not be provided here. To compile:
1. Put the cpp file into /source/utility/
2. Open the CMakeLists.txt file in the same location
3. Add the following:

```cmake
ADD_EXECUTABLE (btree_repacker
  $<TARGET_OBJECTS:star_extern> $<TARGET_OBJECTS:star_core> $<TARGET_OBJECTS:star_base>
  btree_repacker.cpp)
TARGET_LINK_LIBRARIES (btree_repacker ${STAR_EXT_LIBS})
```

4. Run the respective build script for your platform and compile **btree_repacker**.
