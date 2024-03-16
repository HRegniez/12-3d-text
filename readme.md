# Three.js Journey

## What i learnt

````
// font loader import
import { FontLoader } from 'three/examples/jsm/loaders/FontLoader.js'

// Text buffer geometry
import { TextGeometry } from 'three/examples/jsm/geometries/TextGeometry.js'

/**
 * Font
 */ 
const fontLoader = new FontLoader()
fontLoader.load(
    '/fonts/helvetiker_regular.typeface.json',
    (font) => {
        console.log('font loaded !')
        const textGeometry = new TextGeometry(
            'Three.js',
            {
                font: font,
                size: 0.5,
                height: 0.2,
                curveSegments: 5,
                bevelEnabled: true,
                bevelThickness: 0.03,
                bevelSize: 0.02,
                bevelOffset: 0,
                bevelSegments: 4
            }
        )
        const textMaterial = new THREE.MeshBasicMaterial()    
        textMaterial.wireframe = true
        const text = new THREE.Mesh(textGeometry, textMaterial)
        scene.add(text)
    }
)
````

````
        // // Translate to center
        // textGeometry.computeBoundingBox()
        // textGeometry.translate(
        //     - (textGeometry.boundingBox.max.x - 0.2) * 0.5,
        //     - (textGeometry.boundingBox.max.y - 0.2) * 0.5,
        //     - (textGeometry.boundingBox.max.z - 0.3) * 0.5
        // )

        // Center to center
        textGeometry.center()
````


```
        // add donuts
        const donutGeometry = new THREE.TorusGeometry(0.3, 0.2, 20, 45)

        for (let i = 0; i < 500; i++){
            const donut = new THREE.Mesh(donutGeometry, material)

            donut.position.x = (Math.random() - 0.5) * 9
            donut.position.y = (Math.random() - 0.5) * 9
            donut.position.z = (Math.random() - 0.5) * 9

            donut.rotation.x = Math.random() * Math.PI
            donut.rotation.y = Math.random() * Math.PI

            const scale = Math.random()
            donut.scale.set(scale,scale,scale)

            scene.add(donut)
        }
```