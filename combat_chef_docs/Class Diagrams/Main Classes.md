# Actors
```mermaid
classDiagram
	Character <|-- Hero
	Character <|-- Boss
	Character <|-- Mob
	Character *-- HealthBar
	Character *-- StaminaBar
	Character *-- StatsComponent
	ThoughtBubble *-- Hero
	ThoughtBubble *-- Boss
	Hero <-- Player
	class Character {
		Sprite2D sprite_2d
		Area2D hurt_box
		Area2D hit_box
		HealthBar health_bar
		StaminaBar stamina_bar
		StatsComponent stats_component
		AnimationPlayer animation_player
		AnimationStateMachine animation_state
		Timer attack_timer
		+move_character()
	}
	class Hero {
		Area2D interact_box
		ThoughtBubble thought_bubble
		bool can_dash
		enum control_state
		String class
		+hold_item()
		+interact_object()
		+attack()
		exhaust()
		
	}
	class Boss {
		ThoughtBubble thought_bubble
		bool is_raging
		attack_single()
		attack_all()
		environment_effect()
		die()
	}
	class Mob {
		die()
		-spawn_drop()
	}
	class HealthBar {
		increment_health()
		take_damage()
	}
	class StaminaBar {
	}
	class StatsComponent {
	int strength
	int physical_defense
	int magical_defense
	float move_speed
	float attack_speed
	}
	class ThoughtBubble {
	}
	class Player {
		Hero current_hero
		+get_input()
	}
	
```