# Defend the Dojo
```blocks 
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    music.play(music.melodyPlayable(music.pewPew), music.PlaybackMode.InBackground)
    projectile = sprites.createProjectileFromSprite(assets.image`ninjaStar`, Ninja, 0, -100)
    pause(500)
})
scene.onHitWall(SpriteKind.Enemy, function (sprite, location) {
    game.gameOver(false)
})
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    music.play(music.melodyPlayable(music.zapped), music.PlaybackMode.InBackground)
    info.changeScoreBy(1)
    sprites.destroy(sprite)
    sprites.destroy(otherSprite, effects.fire, 500)
})
let Bug: Sprite = null
let projectile: Sprite = null
let Ninja: Sprite = null
scene.setBackgroundImage(assets.image`dojo`)
tiles.setCurrentTilemap(tilemap`floor`)
Ninja = sprites.create(assets.image`Ninja`, SpriteKind.Player)
Ninja.setPosition(75, 100)
controller.moveSprite(Ninja, 75, 0)
info.setScore(0)
game.onUpdateInterval(1000, function () {
    Bug = sprites.createProjectileFromSide(assets.image`bug`, 0, 25)
    Bug.setKind(SpriteKind.Enemy)
    Bug.x = randint(10, 150)
})
```
```template
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    music.play(music.melodyPlayable(music.pewPew), music.PlaybackMode.InBackground)
    projectile = sprites.createProjectileFromSprite(assets.image`ninjaStar`, Ninja, 0, -100)
    pause(500)
})
scene.onHitWall(SpriteKind.Enemy, function (sprite, location) {
    game.gameOver(false)
})
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    music.play(music.melodyPlayable(music.zapped), music.PlaybackMode.InBackground)
    info.changeScoreBy(1)
    sprites.destroy(sprite)
    sprites.destroy(otherSprite, effects.fire, 500)
})
let Bug: Sprite = null
let projectile: Sprite = null
let Ninja: Sprite = null
scene.setBackgroundImage(assets.image`dojo`)
tiles.setCurrentTilemap(tilemap`floor`)
Ninja = sprites.create(assets.image`Ninja`, SpriteKind.Player)
Ninja.setPosition(75, 100)
controller.moveSprite(Ninja, 75, 0)
info.setScore(0)
game.onUpdateInterval(1000, function () {
    Bug = sprites.createProjectileFromSide(assets.image`bug`, 0, 25)
    Bug.setKind(SpriteKind.Enemy)
    Bug.x = randint(10, 150)
})
```
> Open this page [Here](arcade.makecode.com/#tutorial:https://jurakii.github.io/defend-the-dojo-gbs/)

