# 🔫 WeaponMechanics

WeaponMechanics is our "flagship plugin," and you probably already have it installed. If you have WeaponMechanics installed, you can use the following conditions:

***

## In Midair

```yaml
Mechanics:
  - "Message{message=You are in midair} ?InMidair{}"
  - "Message{message=You are not in midair} ?InMidair{inverted=true}"
```

***

## Reloading

```yaml
Mechanics:
  - "Message{message=You are reloading} ?Reloading{}"
  - "Message{message=You are not reloading} ?Reloading{inverted=true}"
```

***

## Right Clicking

```yaml
Mechanics:
  - "Message{message=You are right-clicking} ?RightClicking{}"
  - "Message{message=You are not right-clicking} ?RightClicking{inverted=true}"
```

***

## Scoping

```yaml
Mechanics:
  - "Message{message=You are scoping} ?Scoping{}"
  - "Message{message=You are not scoping} ?Scoping{inverted=true}"
```

***

## Standing

```yaml
Mechanics:
  - "Message{message=You are standing} ?Standing{}"
  - "Message{message=You are not standing} ?Standing{inverted=true}"
```

***

## Swimming

```yaml
Mechanics:
  - "Message{message=You are swimming} ?Swimming{}"
  - "Message{message=You are not swimming} ?Swimming{inverted=true}"
```

***

## Walking

```yaml
Mechanics:
  - "Message{message=You are walking} ?Walking{}"
  - "Message{message=You are not walking} ?Walking{inverted=true}"
```
