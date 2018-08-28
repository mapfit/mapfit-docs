# Cinematography APIs
![](https://files.readme.io/595497a-b8ed89f-orbitanim.gif)
To create a 360° pan animation around a pivot, you can use [OrbitAnimation](ref:orbitanimation) like below.    

```swift

 let callBack: ()->AnimationCallback = {
            struct c : AnimationCallback {
                func onStart() {
                    // invoked when the animation is started
                }

                func onFinish() {
                     // invoked when the animation has ended
                }
            }

            return c() as AnimationCallback
        }

        let pivotPosition = CLLocationCoordinate2D(latitude: 40.743502, longitude: -73.991667)
        // define the options for the animation
        let orbitTrajectory = OrbitTrajectory()
        orbitTrajectory.loop(loop: false)
        orbitTrajectory.pivot(position: pivotPosition, centerToPivot: true, duration: 0.5, easeType: .quartIn)
        orbitTrajectory.duration(duration: 10)
        orbitTrajectory.tiltTo(angle: 2, duration: 4, easeType: .linear)
        orbitTrajectory.zoomTo(zoomLevel: 15, duration: 4, easeType: .linear)
        orbitTrajectory.speedMultiplier(multiplier: 2) /* positive values will rotate anti-clockwise whereas negative values will rotate clockwise */

        // create the animation
        if let mapview = self.mapview {
            let orbitAnimation = Cinematography(mapview)
            let animation = orbitAnimation.create(cameraOptions: orbitTrajectory, cameraAnimationCallback: callBack)

            //start the animation
            animation.start()

          //stop the animation
           animation.stop()

        }

```