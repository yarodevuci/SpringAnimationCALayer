# Animating CALayer with spring effect in iOS with Swift.

This demo app shows how to do spring animation on CALayer. Animation is similar to UIView's method `animateWithDuration(_:delay:usingSpringWithDamping:...)`.

## Usage

1. Copy [SpringAnimation.swift](https://github.com/evgenyneu/SpringAnimationCALayer/blob/master/SpringAnimationCALayer/SpringAnimation.swift) file to your project.
1. Animate your CALayer's property by calling `SpringAnimation.animate` function.

For example, let's rotate a button's layer around its X axis in perspective:

```Swift
let myCALayer = button.layer
var transform = CATransform3DIdentity
transform.m34 = -1.0/100.0
myCALayer.transform = CATransform3DRotate(transform, 0, 1, 0, 0)

SpringAnimation.animate(myCALayer,
                        keypath: "transform.rotation.x",
                        duration: 3.0,
                        usingSpringWithDamping: 0.7,
                        initialSpringVelocity: 1.7,
                        fromValue: M_PI,
                        toValue: 0,
                        onFinished: nil)
```

<img src='https://github.com/evgenyneu/SpringAnimationCALayer/blob/master/graphics/swift_button_flip3.gif?raw=true' width='120' alt='Rotate a button around X axis in iOS/Swift'>



Currently animation looks similar to UIView's method.
But the `duration`, `usingSpringWithDamping` and `initialSpringVelocity` values
are different from those in UIView's method.

## Formula

Here is the formula that I am currently using for animation.

[https://www.desmos.com/calculator/pwcg0pepqy](https://www.desmos.com/calculator/pwcg0pepqy)

<img src='https://raw.githubusercontent.com/evgenyneu/SpringAnimationCALayer/master/graphics/graph/spring_with_damping_formula.png' width='473' alt='Spring animation formula'>


## The Goal

The goal of this project is to make this CALayer's animation work **exactly** like UIView's for the same arguments.

> Help me, Finn and Jake. You're my only hope.

## •ᴥ•

<img src='https://raw.githubusercontent.com/evgenyneu/SpringAnimationCALayer/master/graphics/calayer_animation.gif'  alt='Spring animation for CALayer in iOS with Swift'>
