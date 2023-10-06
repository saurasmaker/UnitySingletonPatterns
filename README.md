
# Unity Singleton Patterns

This namespace contains 3 types of Singleton patterns to use in your Unity projects. 

The namespace "Patterns.Singletons" must be imported.

### Singleton
This class is a Singleton pattern for default class of C#.

## MonoBehaviour Singletons
The generic type T must be the class itself that inherits from SingletonMonoBehaviour.

#### Example 
```
using Patterns.Singletons

public class GameManager : SingletonMonoBehaviourPersistent<GameManager>
{ 
    override protected void OnAwake()
    {
        // TODO: Your functionality.

        /*
         * Equivalent to "void Awake()".
         * Override OnAwake() instead of use 
         * "void Awake()" method.
         */
    }
}
```

It is important to do not use "Awake" method of MonoBehaviour class. It will cause unwanted behavior. Instead of this methods, it is better to use "OnAwake" method that replicate the behavior of the previous one method.

### SingletonMonoBehaviour
All gameobjects that are intended to have a unique instance in the scene must inherit this class.

#### Persistent (Property)
This property will make the gameobject a "DontDestroyOnLoad GameObject.
This action can not be undone.

#### Instance (Property)
Get unique Instance of T class. If the instance has not been initialized, a warning will appear in console notifying that the property will return a "null" value. 

#### ForceInstance (Property)
Get unique Instance of T class. If the instance has not been initialized, the property will generate automatically the GameObject and will instance it adding the corresponding SingletonMonoBehaviour. 

### SingletonMonoBehaviourPersistent
All game objects that are intended to have a single instance in the entire game, regardless of the scene it is in, must inherit this class.

#### Instance (Property)
Get unique Instance of T class. If the instance has not been initialized, a warning will appear in console notifying that the property will return a "null" value. 

#### ForceInstance (Property)
Get unique Instance of T class. If the instance has not been initialized, the property will generate automatically the GameObject and will instance it adding the corresponding SingletonMonoBehaviourPersistent. 
## License

MIT License

Copyright (c) 2023 Iván Saura Cuadrado

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

