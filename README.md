# StageFlow

StageFlow is a domain-specific scripting language for shooting games.

It is designed to control stage timelines such as enemy spawning,
timing, and parameters, while keeping gameplay logic in the engine side.

## Features

- Simple timeline-based scripting
- Frame-based and time-based waiting
- Enemy spawning with parameters
- Easy to read and write

## File Extension

`.stg`

## Example

```stg
:startGame
    spawn enemyBezier x=100 y=50 pattern="spiral" level=2
    wait 1.5s
    repeat 3
        wait 5
    end
