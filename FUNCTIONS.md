# BlitzPRO - New Functions

A list of all functions added to the BlitzPRO

---

## Engine

| Function | Description |
|----------|-------------|
| `EngineSetting setting value` | Sets an internal engine setting |
| `$GetEngineSetting setting` | Gets the current value of an engine setting |

---

## Graphics

| Function | Description |
|----------|-------------|
| `SetBuffer buffer depth=0 pass=0` | Selects a buffer for drawing (extended version with depth and pass parameters for MRT) |
| `ResetBuffer` | Resets all MRTs (1-7) to null |
| `DrawBuffer buffer x y width height blending=1` | Draws buffer contents to screen at specified coordinates with blending mode |
| `DrawBufferRect buffer x y width height srcx srcy srcwidth srcheight blending=1` | Draws a portion of a buffer to screen |
| `%BufferWidth buffer` | Buffer width in pixels |
| `%BufferHeight buffer` | Buffer height in pixels |
| `%BufferDepth buffer` | Buffer color depth (bits per pixel) |
| `%DepthBuffer` | Returns a pointer to the depth buffer |
| `DrawPhysicsDebug aabb=1 mesh=1` | Renders debug visualization of physics bodies (AABB boxes and trimeshes) |
| `%ColorAlpha` | Returns the current alpha channel value of the active color |
| `RoundedRect x y width height radius solid=1 angle=0` | Draws a rectangle with rounded corners |
| `ProgressOval x y width height progress thickness solid=1 angle=0` | Draws an oval progress bar with specified thickness and progress |
| `%BeginBatching` | Begins batch rendering (combines draw calls for performance) |
| `EndBatching` | Ends batch rendering |
| `#MoviePosition movie` | Current playback position of video in seconds |
| `#MovieLength movie` | Video duration in seconds |
| `MovieSeek movie seconds` | Seeks video to the specified position |
| `%LoadAnimImageGrid bmpfile columns rows first count` | Loads an animated image from a grid of frames (by columns and rows) |
| `$ImageName image` | Returns the filename from which the image was loaded |
| `%ImageAngle image` | Returns the image angle set by RotateImage |
| `ColorImage image r g b a` | Set color image |
| `ShaderImage image effect` | Set image effect |
| `TurnImage image angle` | Rotates an image by the specified angle (relative to current state) |

---

## Textures

| Function | Description |
|----------|-------------|
| `TexturePersistentCaching enable` | Enables/disables persistent texture caching (textures stay in memory) |
| `%ClearUnusedTextures` | Clears unused textures from cache. Returns the number of removed textures |
| `%LoadAnimTextureGrid file flags columns rows first count` | Loads an animated texture from a grid layout (by columns and rows) |
| `TextureDivisor div` | Sets the texture size divisor on loading |
| `FilterTexture texture filter` | Sets the texture filtering mode, point, linear, etc.. |
| `%TextureFlags texture` | Returns the texture flags |
| `%GetTextureFilter match_text` | Searches for a texture filter by mask. Returns flags |
| `AwaitTextures` | Waits for all asynchronous texture loads to complete |

---

## Brushes

| Function | Description |
|----------|-------------|
| `BrushMaterial brush roughness metallic` | Sets PBR material properties (roughness and metallic) for a brush |
| `BrushEffect brush effect` | Applies a shader effect to a brush |
| `BrushEffectBool brush var value semantic=0` | Sets a boolean shader parameter on a brush |
| `BrushEffectInt brush var value semantic=0` | Sets an integer shader parameter on a brush |
| `BrushEffectFloat brush var value semantic=0` | Sets a float shader parameter on a brush |
| `BrushEffectVector brush x=0 y=0 z=0 w=0 semantic=0` | Sets a vector shader parameter on a brush |
| `BrushEffectMatrix brush var value semantic=0` | Sets a matrix shader parameter on a brush |
| `BrushEffectTexture brush var tex semantic=0` | Binds a texture to a shader parameter on a brush |
| `BrushEffectBoolArray brush var bnk semantic=0` | Sets an array of boolean shader parameters on a brush from a bank |
| `BrushEffectIntArray brush var bnk semantic=0` | Sets an array of integer shader parameters on a brush from a bank |
| `BrushEffectFloatArray brush var bnk semantic=0` | Sets an array of float shader parameters on a brush from a bank |
| `BrushEffectVectorArray brush var bnk semantic=0` | Sets an array of vector shader parameters on a brush from a bank |
| `BrushEffectMatrixArray brush var bnk semantic=0` | Sets an array of matrix shader parameters on a brush from a bank |
| `%GetBrushBlend brush` | Returns the brush blend mode |
| `GetBrushColor brush rptr gptr bptr` | Returns the brush color via component pointers |

---

## Meshes

| Function | Description |
|----------|-------------|
| `%FindMesh file` | Searches for an already loaded mesh by filename. Returns a pointer |
| `%CreateMeshCube mesh parent=0` | Creates a cube from an mesh AABB |
| `%WeldMesh mesh epsilon` | Welds nearby vertices of a mesh within the given tolerance. Returns a new mesh |
| `MeshThickness mesh thickness` | Computes mesh collisions volume for physics |
| `UpdateTB mesh` | Recalculates tangent and binormal vectors |
| `#MeshX mesh minmax` | Returns the minimum (minmax=0) or maximum (minmax=1) X coordinate of a mesh |
| `#MeshY mesh minmax` | Returns the minimum or maximum Y coordinate of a mesh |
| `#MeshZ mesh minmax` | Returns the minimum or maximum Z coordinate of a mesh |
| `GetCullBox mesh x y z width height depth` | Gets the culling bounding box of a mesh |
| `GetMeshBox mesh x y z width height depth` | Gets the exact bounding box of a mesh |

---

## Shader Effects

| Function | Description |
|----------|-------------|
| `%LoadEffect file defs=""` | Loads a shader effect from file with optional preprocessor defines |
| `%ReloadEffect effect file defs=""` | Reloads a shader effect from file |
| `FreeEffect effect` | Frees a shader effect |
| `$GetEffectError` | Returns the error text from the last shader load |
| `%EffectTexture effect var tex semantic=0` | Binds a texture to a shader variable |
| `%EffectTechnique effect var` | Sets the active technique (pass) of a shader effect |
| `EffectBool effect var value semantic=0` | Sets a boolean shader parameter |
| `EffectInt effect var value semantic=0` | Sets an integer shader parameter |
| `EffectFloat effect var value semantic=0` | Sets a float shader parameter |
| `EffectVector effect x=0 y=0 z=0 w=0 semantic=0` | Sets a vector shader parameter |
| `EffectMatrix effect var value semantic=0` | Sets a matrix shader parameter |
| `EffectBoolArray effect var bnk semantic=0` | Sets an array of boolean shader parameters from a bank |
| `EffectIntArray effect var bnk semantic=0` | Sets an array of integer shader parameters from a bank |
| `EffectFloatArray effect var bnk semantic=0` | Sets an array of float shader parameters from a bank |
| `EffectVectorArray effect var bnk semantic=0` | Sets an array of vector shader parameters from a bank |
| `EffectMatrixArray effect var bnk semantic=0` | Sets an array of matrix shader parameters from a bank |
| `%EffectHasSemantic effect var` | Checks if a shader variable has a given semantic |
| `%EffectHasVariable effect var` | Checks if a variable exists in a shader |

---

## Shadow Manager

| Function | Description |
|----------|-------------|
| `%ShadowManagerCreateSlot` | Creates a slot for rendering a shadow map |
| `ShadowManagerFreeSlot slot` | Frees a shadow map slot |
| `ShadowManagerSetParams bias slope caster_mask tween` | Sets shadow manager parameters (bias, slope, caster mask, tween) |
| `ShadowManagerRenderPoint slot buff depth effect cam x0 y0 z0 x y z range` | Renders a shadow map from a point light source |
| `ShadowManagerRenderSpot slot buff depth effect cam x0 y0 z0 pitch0 yaw0 x y z pitch yaw range fov` | Renders a shadow map from a spotlight |
| `ShadowManagerRenderDir slot buff depth effect cam x0 y0 z0 pitch0 yaw0 x y z pitch yaw extrusion cascades split maxfar` | Renders a shadow map from a directional light (cascaded shadows) |

---

## Camera

| Function | Description |
|----------|-------------|
| `CameraFX camera settings` | Sets camera effects |
| `CameraMask camera mask` | Sets the display bitmask for a camera |
| `%GetCameraFX camera` | Returns the current camera effect settings |
| `CameraDepthBias camera bias slopebias` | Sets depth bias for a camera (combats z-fighting) |
| `%CameraMatrix camera typ tween=1` | Returns a camera matrix by type with interpolation |

---

## Audio

| Function | Description |
|----------|-------------|
| `%EmitMusic filename entity mode=0` | Plays music attached to an entity |
| `%EmitChannel chn entity` | Attached already created channel to an entity |
| `SoundPause sound pause` | Pauses or unpauses a sound object (affects all playbacks of this sound) |
| `%CreateChannel samplerate channels` | Creates a custom audio channel for streaming PCM data (PCM 16-bit signed, little-endian) |
| `ChannelSeek channel seconds` | Seeks an audio channel to the specified position in seconds |
| `#ChannelLength channel` | Audio channel duration in seconds |
| `#ChannelPosition channel` | Current position of an audio channel in seconds |
| `SoundRange sound mindist maxdist` | Sets 3D sound range (volume falloff distance) for a sound object. Works with EmitSound/EmitMusic |
| `ChannelRange channel mindist maxdist` | Sets 3D sound range for an already-playing channel. Works with EmitSound/EmitMusic |
| `%ChannelAvail channel` | Returns the number of bytes available for reading from a channel |
| `%ChannelPushData channel bank offset count` | Pushes raw PCM16 audio data from a bank into a custom channel |
| `%ChannelGetData channel bank offset count` | Reads PCM16 audio data from a channel into a bank |
| `ChannelFlush channel` | Flushes all buffered audio data in a channel |
| `#ChannelLevel channel` | Returns the current peak output level of a sound channel (0.0 = silence) |
| `ChannelReverb channel wetlevel drylevel decaytime hfdecayratio dsp` | Adds a reverb effect to a channel. Returns DSP handle |
| `ChannelEcho channel delay feedback drylevel wetlevel dsp` | Adds an echo effect to a channel |
| `ChannelChorus channel mix rate depth dsp` | Adds a chorus effect to a channel |
| `ChannelFlanger channel mix depth rate dsp` | Adds a flanger effect to a channel |
| `ChannelDistortion channel level dsp` | Adds a distortion effect to a channel |
| `ChannelLowpass channel cutoff resonance dsp` | Adds a low-pass filter to a channel |
| `ChannelHighpass channel cutoff resonance dsp` | Adds a high-pass filter to a channel |
| `ChannelPitchShift channel pitch dsp` | Adds a pitch shift effect to a channel |
| `ChannelCompressor channel threshold ratio attack release gainmakeup dsp` | Adds a compressor effect to a channel |
| `ChannelParamEQ channel center bandwidth gain dsp` | Adds a parametric EQ to a channel |
| `ChannelTremolo channel frequency depth dsp` | Adds a tremolo effect to a channel |
| `ChannelClearDSP channel` | Removes all DSP effects from a channel |
| `ChannelRemoveDSP channel dsp` | Removes a specific DSP effect from a channel |
| `%CreateRecorder device samplerate channels` | Creates an audio recording channel (PCM 16-bit signed, little-endian) |
| `%CountRecordingDevices` | Returns the number of available audio recording devices |
| `$RecordingDeviceName device` | Returns the name of the specified recording device (1-based index) |

---

## Entities

| Function | Description |
|----------|-------------|
| `#GetEntityAlpha entity` | Returns the current transparency of an entity |
| `%EntityColorR entity` | Returns the red component of an entity's color |
| `%EntityColorG entity` | Returns the green component of an entity's color |
| `%EntityColorB entity` | Returns the blue component of an entity's color |
| `%GetEntityBlend entity` | Returns the blend mode of an entity |
| `%GetEntityTexture entity tid` | Returns a texture of an entity by index |
| `GetEntityPickMode entity pickable obscurer` | Returns the pick mode of an entity (pickability and obscuring) |
| `EntityCylinder entity x_radius y_radius=0` | Sets a cylindrical collision shape for an entity |
| `GetEntityShape entity x y z width height depth` | Returns the collision shape parameters of an entity |
| `EntityInstance entity parent` | Copies an entity with shared data |
| `%GetInstance entity` | Returns the pointer to the original entity from an instance |
| `CaptureEntity entity` | Captures the current state of an entity for frame-by-frame playback |
| `%EntityExists entity` | Checks if an entity still exists in memory |
| `$EntityFilename entity` | Returns the filename from which the entity was loaded |
| `MaskEntity entity mask` | Sets the display bitmask for an entity |
| `%EntityMask entity` | Returns the display bitmask of an entity |
| `EntityDestructor entity funcptr` | Sets a callback function to be called when the entity is destroyed |
| `EntityEffectBool entity var value semantic=0` | Sets a boolean shader parameter on an entity |
| `EntityEffectInt entity var value semantic=0` | Sets an integer shader parameter on an entity |
| `EntityEffectFloat entity var value semantic=0` | Sets a float shader parameter on an entity |
| `EntityEffectVector entity x=0 y=0 z=0 w=0 semantic=0` | Sets a vector shader parameter on an entity |
| `EntityEffectMatrix entity var value semantic=0` | Sets a matrix shader parameter on an entity |
| `EntityEffectTexture entity var tex semantic=0` | Binds a texture to a shader parameter on an entity |
| `EntityEffectBoolArray entity var bnk semantic=0` | Sets an array of boolean shader parameters on an entity's brush from a bank |
| `EntityEffectIntArray entity var bnk semantic=0` | Sets an array of integer shader parameters on an entity's brush from a bank |
| `EntityEffectFloatArray entity var bnk semantic=0` | Sets an array of float shader parameters on an entity's brush from a bank |
| `EntityEffectVectorArray entity var bnk semantic=0` | Sets an array of vector shader parameters on an entity's brush from a bank |
| `EntityEffectMatrixArray entity var bnk semantic=0` | Sets an array of matrix shader parameters on an entity's brush from a bank |

---

## Physics

| Function | Description |
|----------|-------------|
| `EntityMass entity mass` | Sets the mass of an entity for the physics simulator |
| `EntityKinematic entity kinematic` | Switches an entity to kinematic mode (static, but can be moved) |
| `EntityPhysics entity enable` | Enables/disables the physics simulator for an entity |
| `EntityActivate entity enable` | Activates/deactivates a physics body |
| `EntitySleep entity allow` | Allows/disallows a body to enter sleep mode (optimization) |
| `EntityFreeze entity enable` | Freezes a physics body (stops simulation) |
| `%EntityIsActive entity` | Checks if a physics body is active |
| `%EntityIsFreezed entity` | Checks if a physics body is frozen |
| `EntityCenter entity x y z` | Sets the center of mass of a physics body |
| `EntityLinearCast entity enable` | Enables/disables linear casting (collision detection during movement) |
| `EntityFriction entity friction` | Sets the friction coefficient of an entity |
| `EntityRollFriction entity friction` | Sets the rolling friction coefficient |
| `EntityRestitution entity res` | Sets the restitution (bounciness) coefficient of an entity |
| `EntityLinearVelocity entity x y z` | Sets the linear velocity of an entity |
| `EntityAngularVelocity entity x y z` | Sets the angular velocity of an entity |
| `GetEntityLinearVelocity entity x=0 y=0 z=0` | Returns the linear velocity of an entity via pointers |
| `GetEntityAngularVelocity entity x=0 y=0 z=0` | Returns the angular velocity of an entity via pointers |
| `EntityImpulse entity x y z` | Applies an impulse to an entity (instant velocity change) |
| `EntityTorque entity x y z` | Applies a torque to an entity |
| `EntityGravity entity factor` | Sets the gravity multiplier for an entity |
| `EntityLinearFactor entity x y z` | Limits entity movement per axis (0 = locked, 1 = free) |
| `EntityAngularFactor entity x y z` | Limits entity rotation per axis |
| `EntityLinearDamping entity damping` | Sets linear damping (deceleration over time) |
| `EntityAngularDamping entity damping` | Sets angular damping |
| `EntityConstraint entity normal_angle plane_angle twist_min_angle twist_max_angle torque_friction` | Configures a hinge joint constraint for an entity |
| `EntityClearForces entity` | Fully resets all forces acting on an entity |

---

## Collisions

| Function | Description |
|----------|-------------|
| `#CollisionImpulse entity collision_index` | Returns the collision impulse (force) |
| `#CollisionDistance entity collision_index` | Returns the distance traveled before collision |

---

## Effekseer (Particle Effects)

| Function | Description |
|----------|-------------|
| `%LoadEffekseer file scale=1` | Loads an Effekseer particle effect from file with a scale factor |
| `FreeEffekseer effekseer` | Frees a particle effect |
| `%PlayEffekseer effekseer parent=0 repeats=1` | Plays a particle effect (optionally attached to an entity, with repeats) |
| `StopEffekseer instance` | Stops a particle effect playback |
| `SetEffekseerSpeed instance speed` | Sets the playback speed of a particle effect |
| `PauseEffekseer instance pause` | Pauses/resumes particle effect playback |
| `%EffekseerPlaying instance` | Checks if a particle effect is currently playing |

---

## Soft Body

| Function | Description |
|----------|-------------|
| `%SoftBody mesh stiffness=0 pressure=0` | Converts a mesh into a soft body with given stiffness and pressure |
| `SoftStiffness mesh stiffness` | Sets the stiffness of a soft body |
| `SoftPressure mesh pressure` | Sets the internal pressure of a soft body |
| `SoftDamping mesh damping` | Sets the damping of a soft body |
| `SoftPin mesh surface vertex` | Pins a soft body vertex in space |
| `SoftUnPin mesh surface vertex` | Unpins a soft body vertex |
| `SoftPinAt mesh x y z radius` | Pins all vertices within a given radius of a point |
| `SoftUnPinAll mesh` | Unpins all vertices of a soft body |
| `SoftImpulse mesh x y z` | Applies an impulse to a soft body |
| `%IsSoftBody mesh` | Checks if a mesh is a soft body |

---

## Multithreading

| Function | Description |
|----------|-------------|
| `CallAsync` | Calls an thread function by func pointer with 16 args limit |
| `CreateAsyncStream% id%` | Creates an async message stream |
| `StopAsyncStream stream%` | Stops and frees an async stream |
| `SendAsyncMsg stream% id% wait%` | Sends a message through async stream |
| `RecvAsyncMsg% stream%` | Receives a message from async stream |
| `LockMutex id%` | Locks a mutex by id |
| `UnlockMutex id%` | Unlocks a mutex by id |
| `TryLockMutex% id%` | Tries to lock a mutex without waiting |

---

## Input

| Function | Description |
|----------|-------------|
| `CombineKeys flush` | Combine mousehits and keyhits into one. Makes mouse buttons 1 to 7 readable as keyboard keys (keys 256 to 262). |

---

## File System

| Function | Description |
|----------|-------------|
| `%FileTime file` | Returns the last modification time of a file |

---

## Bank

| Function | Description |
|----------|-------------|
| `%BankExists bank` | Checks if a bank exists in memory |
| `%BankPointer bank` | Returns a pointer to the raw data of a bank |

---

## New tokens

| Function | Description |
|-------|--------|
| `FuncPtr` | Gets function pointer |
| `VarPtr` | Variable or object variable pointer |
| `TypePtr` | Type pointer |
| `CastPtr` | Cast int ptr to object or funcvar |
| `Deref$%#.` | Dereference variable pointer for value set |

---

## No longer supported

| Function | Description |
|----------|-------------|
| `HWMultiTex enable` | Hardware multitexturing toggle |
| `WBuffer enable` | W-buffer control. Use CameraFX with 4 flag instead. |
| `Dither enable` | Dithering toggle |