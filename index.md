<!doctype html>
<html>
    <head>
        <script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
        <script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar.js"></script>
        <script src="https://raw.githack.com/donmccurdy/aframe-extras/master/dist/aframe-extras.loaders.min.js"></script>
        <script src="https://raw.githack.com/AR-js-org/studio-backend/master/src/modules/marker/tools/gesture-detector.js"></script>
        <script src="https://raw.githack.com/AR-js-org/studio-backend/master/src/modules/marker/tools/gesture-handler.js"></script>
    </head>

    <body style="margin: 0; overflow: hidden;">
        <a-scene
            vr-mode-ui="enabled: false;"
            loading-screen="enabled: false;"
            renderer="logarithmicDepthBuffer: true;"
            arjs="trackingMethod: best; sourceType: webcam; debugUIEnabled: false;"
            id="scene"
            embedded
            gesture-detector
        >
            <a-assets>
                <a-asset-item
                    id="animated-asset"
                    src="https://raw.githubusercontent.com/guarim/realarjs.github.io/main/Abeille qui virevolte.glb"
                ></a-asset-item>
            </a-assets>

            <a-marker
                id="animated-marker"
                type="pattern"
                preset="custom"
                url="https://raw.githubusercontent.com/guarim/realarjs.github.io/main/marker.patt"
                raycaster="objects: .clickable"
                emitevents="true"
                cursor="fuse: false; rayOrigin: mouse;"
                id="markerA"
            >
                <a-entity
                    id="bowser-model"
                    rotation="-75 0 0"
                    position="1 1 1"
                    scale="0.1432144704496557 0.1432144704496557 0.1432144704496557"
                    animation-mixer="loop: repeat"
                    gltf-model="#animated-asset"
                    class="clickable"
                    gesture-handler
                ></a-entity>
            </a-marker>

            <a-entity camera></a-entity>
        </a-scene>
    </body>
</html>
