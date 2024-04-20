classDiagram
    class Player {
        <<abstract>>
        +String name
        +Weapon[] weapons
        +attack(target: Enemy): void
    }
    class Enemy {
        <<abstract>>
        +String name
        +Weapon[] weapons
        +attack(target: Player): void
    }
    class Weapon {
        -String type
        -float power
        -int bulletsLeft
    }
    class FiringGun {
        -int bulletsLeft
    }
    class Sword {
        -float bladeLength
    }

    Player <|-- MiniGame.Player
    Enemy <|-- MiniGame.Enemy
    Weapon <|-- FiringGun
    Weapon <|-- Sword

    Player "1" o-- "2" Weapon
    Enemy "1" o-- "3" Weapon
