import random
import time

normal_enemy_act_list = ["strike", "powerful strike", "miss", "critical strike"]



player = {}
unarmed = {}
light_armed = {}
moderate_armed = {}
heavy_armed = {}
mini_boss = {}
boss = {}
mega_boss = {}

player["max health"] = 999999999999999999999999999999999999999999999999999999999999999
player["health"] = 999999999999999999999999999999999999999999999999999999999999999
unarmed["health"] = 10
light_armed["health"] = 25
moderate_armed["health"] = 60
heavy_armed["health"] = 150
mini_boss["health"] = 500
boss["health"] = 2000
mega_boss["health"] = 10000

player["cap damage"] = 999
unarmed["cap damage"] = 3
light_armed["cap damage"] = 7
moderate_armed["cap damage"] = 20
heavy_armed["cap damage"] = 50
mini_boss["cap damage"] = 150
boss["cap damage"] = 300
mega_boss["cap damage"] = 1000

unarmed["cap xp"] = 3
light_armed["cap xp"] = 7
moderate_armed["cap xp"] = 20
heavy_armed["cap xp"] = 50
mini_boss["cap xp"] = 150
boss["cap xp"] = 500
mega_boss["cap xp"] = 2000


player["xp required"] = 10
player["xp"] = 0
player["level"] = 0

lvl_up_count = 0
turn_skip = 0
burn_round_counter = 0
burn_level = 0

while True:
    player_health = 0
    burn_round_counter = 0
    turn_skip = 0
    enemy_choice = input("Which enemy would you like to test? The enemies are: \nUnarmed \nLight Armed \nModerate Armed \nHeavy Armed \nMini Boss \nBoss \nMega Boss \n")
    enemy_choice_lower = enemy_choice.lower()
    if enemy_choice_lower == "unarmed":
        unarmed["health"] = 10
        print("Seems like you encountered an unarmed!")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    unarmed["health"] = unarmed["health"] - player_damage
                    unarmed_health_str = str(unarmed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The unarmed has " + unarmed_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    unarmed["health"] = unarmed["health"] - player_damage
                    unarmed_health_str = str(unarmed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The unarmed has " + unarmed_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if unarmed["health"] <= 0:
                turn_skip = 0
                print("The unarmed has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, unarmed["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                time.sleep(2)
                break
            enemy_attack_d10 = random.randint(1,10)
            if enemy_attack_d10 >= 1 and enemy_attack_d10 <= 5: #strike
                enemy_damage = random.randint(1, unarmed["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The unarmed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 >= 6 and enemy_attack_d10 <= 7: #powerful strike
                enemy_damage = random.randint(1, unarmed["cap damage"]*2)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The unarmed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 == 10: #critical strike
                enemy_damage = random.randint(1, unarmed["cap damage"]*4)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The unarmed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            else:
                print("The unarmed missed their attack!")
                time.sleep(2)
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "light armed":
        light_armed["health"] = 25
        print("Seems like you encountered a light armed!")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    light_armed["health"] = light_armed["health"] - player_damage
                    light_armed_health_str = str(light_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The light armed has " + light_armed_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    light_armed["health"] = light_armed["health"] - player_damage
                    light_armed_health_str = str(light_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The light armed has " + light_armed_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if light_armed["health"] <= 0:
                turn_skip = 0
                print("The light armed has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, light_armed["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                time.sleep(2)
                break
            enemy_attack_d10 = random.randint(1,10)
            if enemy_attack_d10 >= 1 and enemy_attack_d10 <= 5: #strike
                enemy_damage = random.randint(1, light_armed["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The light armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 >= 6 and enemy_attack_d10 <= 7: #powerful strike
                enemy_damage = random.randint(1, light_armed["cap damage"]*2)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The light armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 == 10: #critical strike
                enemy_damage = random.randint(1, light_armed["cap damage"]*4)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The light armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            else:
                print("The light armed missed their attack!")
                time.sleep(2)
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "moderate armed":
        moderate_armed["health"] = 60
        print("Seems like you encountered a moderate armed!")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    moderate_armed["health"] = moderate_armed["health"] - player_damage
                    moderate_armed_health_str = str(moderate_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The moderate armed has " + moderate_armed_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    moderate_armed["health"] = moderate_armed["health"] - player_damage
                    moderate_armed_health_str = str(moderate_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The moderate armed has " + moderate_armed_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if moderate_armed["health"] <= 0:
                turn_skip = 0
                print("The moderate armed has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, moderate_armed["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                while True:
                    if player["xp"] >= player["xp required"]:
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "!")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                time.sleep(2)
                break
            enemy_attack_d10 = random.randint(1,10)
            if enemy_attack_d10 >= 1 and enemy_attack_d10 <= 5: #strike
                enemy_damage = random.randint(1, moderate_armed["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The moderate armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 >= 6 and enemy_attack_d10 <= 7: #powerful strike
                enemy_damage = random.randint(1, moderate_armed["cap damage"]*2)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The moderate armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 == 10: #critical strike
                enemy_damage = random.randint(1, moderate_armed["cap damage"]*4)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The moderate armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            else:
                print("The moderate armed missed their attack!")
                time.sleep(2)
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "heavy armed":
        heavy_armed["health"] = 150
        print("Seems like you encountered a heavy armed!")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    heavy_armed["health"] = heavy_armed["health"] - player_damage
                    heavy_armed_health_str = str(heavy_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The heavy armed has " + heavy_armed_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    heavy_armed["health"] = heavy_armed["health"] - player_damage
                    heavy_armed_health_str = str(heavy_armed["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The heavy armed has " + heavy_armed_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if heavy_armed["health"] <= 0:
                turn_skip = 0
                print("The heavy armed has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, heavy_armed["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                break
            enemy_attack_d10 = random.randint(1,10)
            if enemy_attack_d10 >= 1 and enemy_attack_d10 <= 5: #strike
                enemy_damage = random.randint(1, heavy_armed["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The heavy armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 >= 6 and enemy_attack_d10 <= 7: #powerful strike
                enemy_damage = random.randint(1, heavy_armed["cap damage"]*2)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The heavy armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            elif enemy_attack_d10 == 10: #critical strike
                enemy_damage = random.randint(1, heavy_armed["cap damage"]*4)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The heavy armed dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
            else:
                print("The heavy armed missed their attack!") #miss
                time.sleep(2)
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "mini boss":
        print("Seems you encountered a mini boss!")
        time.sleep(2)
        print("A decently powerful foe.")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    mini_boss["health"] = mini_boss["health"] - player_damage
                    mini_boss_health_str = str(mini_boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The mini boss has " + mini_boss_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    mini_boss["health"] = mini_boss["health"] - player_damage
                    mini_boss_health_str = str(mini_boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The mini boss has " + mini_boss_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if mini_boss["health"] <= 0:
                turn_skip = 0
                print("The mini boss has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, mini_boss["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                break
            boss_act_d25 = random.randint(1,25)
            if boss_act_d25 >= 0 and boss_act_d25 <= 18: #strike
                enemy_damage = random.randint(1, mini_boss["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The mini boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d10 = random.randint(1,10)
                if burn_d10 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 1
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
            elif boss_act_d25 >= 19 and boss_act_d25 <=23: #critical
                enemy_damage = random.randint(1, mini_boss["cap damage"]*3)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The mini boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d5 = random.randint(1,5)
                if burn_d5 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 1
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
                elif boss_act_d25 == 24:
                    print("The mini boss missed their attack!") #miss
                    time.sleep(2)
                else:
                    turn_skip = turn_skip + random.randint(1,2) #stun
                    turn_skip_str = str(turn_skip)
                    print("The mini boss hit you severely!")
                    time.sleep(2)
                    print("You are stunned for " + turn_skip_str + " rounds!")
                    time.sleep(2)
            if burn_round_counter >= 1:
                print("Burn effects you!")
                time.sleep(2)
                burn_damage = round(player["health"]*burn_level/10)
                player["health"] = player["health"] - burn_damage
                player_health_str = str(player["health"])
                burn_round_counter = burn_round_counter - 1
                burn_round_counter_str = str(burn_round_counter)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                print("You will be burning for " + burn_round_counter_str + " more round(s)")
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "boss":
        print("Seems you encountered a boss!")
        time.sleep(2)
        print("A pretty powerful one.")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    boss["health"] = boss["health"] - player_damage
                    boss_health_str = str(boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The boss has " + boss_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    boss["health"] = boss["health"] - player_damage
                    boss_health_str = str(boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The boss has " + boss_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if boss["health"] <= 0:
                turn_skip = 0
                print("The boss has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, boss["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                break
            boss_act_d25 = random.randint(1,25)
            if boss_act_d25 >= 0 and boss_act_d25 <= 18: #strike
                enemy_damage = random.randint(1, boss["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d10 = random.randint(1,10)
                if burn_d10 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 3
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
            elif boss_act_d25 >= 19 and boss_act_d25 <=23: #critical
                enemy_damage = random.randint(1, boss["cap damage"]*3)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d5 = random.randint(1,5)
                if burn_d5 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 3
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
                elif boss_act_d25 == 24:
                    print("The boss missed their attack!") #miss
                    time.sleep(2)
                else:
                    turn_skip = turn_skip + random.randint(1,3) #stun
                    turn_skip_str = str(turn_skip)
                    print("The boss hit you severely!")
                    time.sleep(2)
                    print("You are stunned for " + turn_skip_str + " rounds!")
                    time.sleep(2)
            if burn_round_counter >= 1:
                print("Burn effects you!")
                time.sleep(2)
                burn_damage = round(player["health"]*burn_level/10)
                player["health"] = player["health"] - burn_damage
                player_health_str = str(player["health"])
                burn_round_counter = burn_round_counter - 1
                burn_round_counter_str = str(burn_round_counter)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                print("You will be burning for " + burn_round_counter_str + " more round(s)")
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    elif enemy_choice_lower == "mega boss":
        print("Seems you encountered a mega boss!")
        time.sleep(2)
        print("The supreme of all!")
        time.sleep(2)
        print("Best of luck! You will need it.")
        time.sleep(2)
        while True:
            if turn_skip == 0:
                action = input("What would you like to do? (strike or powerful strike) \n")
                action_lower = action.lower()
                if action_lower == "strike":
                    player_damage = random.randint(0, player["cap damage"])
                    player_damage_str = str(player_damage)
                    mega_boss["health"] = mega_boss["health"] - player_damage
                    mega_boss_health_str = str(mega_boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The mega boss has " + mega_boss_health_str + " health left!")
                    time.sleep(2)
                elif action_lower == "powerful strike":
                    player_damage = random.randint(0, player["cap damage"]*2)
                    player_damage_str = str(player_damage)
                    mega_boss["health"] = mega_boss["health"] - player_damage
                    mega_boss_health_str = str(mega_boss["health"])
                    print("You dealt " + player_damage_str + " damage!")
                    time.sleep(2)
                    if player_damage == 0:
                        print("Which means you missed!")
                        time.sleep(2)
                    print("The mega boss has " + mega_boss_health_str + " health left!")
                    time.sleep(2)
                    turn_skip = turn_skip + 1
                    print("You wasted your energy a lot!")
                    time.sleep(2)
                    print("You wont be able to do anything for 1 round.")
                    time.sleep(2)
                else:
                    print("Please write strike or powerful strike!")
                    time.sleep(2)
                    continue
            else:
                print("You are too tired to do anything! You skipped this round.")
                turn_skip = turn_skip - 1
                turn_skip_str = str(turn_skip)
                time.sleep(2)
                print("You will be stunned for " + turn_skip_str + " more rounds!")
                time.sleep(2)
            if mega_boss["health"] <= 0:
                turn_skip = 0
                print("The mega boss has no hp left!")
                time.sleep(2)
                print("You won the battle!")
                time.sleep(2)
                xp_gained = random.randint(0, mega_boss["cap xp"])
                xp_gained_str = str(xp_gained)
                player["xp"] = player["xp"] + xp_gained
                print("You earned " + xp_gained_str + " xp! \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                
                while True:
                    if player["xp"] >= player["xp required"]:
                        lvl_up_count = lvl_up_count + 1
                        player["level"] = player["level"] + 1
                        player["health"] = round(player["health"]*1.25)
                        player["cap damage"] = round(player["cap damage"]*1.25)
                        player["xp"] = player["xp"] - player["xp required"]
                        player["xp required"] = round(player["xp required"]*1.5)
                        time.sleep(2)
                        print("You leveled up to level " + str(player["level"]) + "! (x" + str(lvl_up_count) + ")")
                        time.sleep(2)
                    else:
                        lvl_up_count = 0
                        break
                print("Your xp now: \n" + str(player["xp"]) + "/" + str(player["xp required"]))
                break
            mega_boss_act_d200 = random.randint(1,200)
            if mega_boss_act_d200 >= 0 and mega_boss_act_d200 <= 134: #strike
                enemy_damage = random.randint(1, mega_boss["cap damage"])
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The mega boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d10 = random.randint(1,10)
                if burn_d10 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 3
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
            elif mega_boss_act_d200 >= 135 and mega_boss_act_d200 <= 169: #critical
                enemy_damage = random.randint(1, mega_boss["cap damage"]*3)
                player["health"] = player["health"] - enemy_damage
                enemy_damage_str = str(enemy_damage)
                player_health_str = str(player["health"])
                print("The mega boss dealt " + enemy_damage_str + " damage!")
                time.sleep(2)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                burn_d5 = random.randint(1,5)
                if burn_d5 == 5:
                    burn_round_counter = burn_round_counter + random.randint(1,3)
                    burn_round_counter_str = str(burn_round_counter)
                    burn_level = 3
                    print("The strike caused you to start burning!")
                    time.sleep(2)
                    print("Now you will be burning for " + burn_round_counter_str + " rounds!")
                    time.sleep(2)
            elif mega_boss_act_d200 >= 170 and mega_boss_act_d200 <= 194:
                print("The mega boss missed their attack!") #miss
                time.sleep(2)
            elif mega_boss_act_d200 >= 195 and mega_boss_act_d200 <= 199:
                turn_skip = turn_skip + random.randint(1,3) #stun
                turn_skip_str = str(turn_skip)
                print("The mega boss hit you severely!")
                time.sleep(2)
                print("You are stunned for " + turn_skip_str + " rounds!")
                time.sleep(2)
            else:
                print("The boss goes insane!")
                time.sleep(2)
                player["health"] = 0
                print("The boss put you down in one hit!")
                time.sleep(2)
            if burn_round_counter >= 1:
                print("Burn effects you!")
                time.sleep(2)
                burn_damage = round(player["health"]*burn_level/10)
                player["health"] = player["health"] - burn_damage
                player_health_str = str(player["health"])
                burn_round_counter = burn_round_counter - 1
                burn_round_counter_str = str(burn_round_counter)
                print("You have " + player_health_str + " health left!")
                time.sleep(2)
                print("You will be burning for " + burn_round_counter_str + " more round(s)")
            if player["health"] <= 0:
                turn_skip = 0
                print("You have no hp left!")
                time.sleep(2)
                print("You lost the battle!")
                time.sleep(2)
                break
    else:
        print("Please type one of those below!")
        time.sleep(2)
