# %% imports
import random
import collections
# %% variables
variables = { ## All variables in the program
    "turn": 0,
    "encounter_choices": 0,
    "catch_chance": 0,
    "party_change": 0,
    "crit_catch": 100,
    "shiny_chance": 1000,
    "buy_options": 0,
    "money": 1000,
    "in_shop": 0,
    "purchases": 0,
    "first_turn": 0,
    "encounter": 0,
    "moving_pokemon": 0,
    "moving_var": 0,
    "reorder": 0,
    "catch_rate": 0,
    "action": 0,
    "encounter_values": 0,
    "encounter_name": 0,
    "box_swap": 0,
    "moving_party": 0,
    "moving_pokemon_party": 0,
    "encounter_name": 0,
    "encounter_caught": 0,
    "encounter_amount_caught": 0,
    "encounter_shiny_caught": 0,
    "encounter_type": 0,
    "encounter_catch_rate": 0,
    "list_of_keys_party": 0,
    "merged": 0,
    "reordered_dict_party": 0,
    "list_of_keys_box": 0,
    "reordered_dict_box": 0,
    "dex_number": 0,
    "encounter_type_2": 0,
    "type_2": 0,
    "has_type_2": 0,
}
# %% pokedex
## All info about encounter pokemon
pokedex = [
    {"name": 'Bulbasaur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Poison',"dex_number": 1},
    {"name": 'Ivysaur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Poison',"dex_number": 2},
    {"name": 'Venusaur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Poison',"dex_number": 3},
    {"name": 'Charmander', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 4},
    {"name": 'Charmeleon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 5},
    {"name": 'Charizard', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Flying',"dex_number": 6},
    {"name": 'Squirtle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 7},
    {"name": 'Wartortle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 8},
    {"name": 'Blastoise', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 9},
    {"name": 'Caterpie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 10},
    {"name": 'Metapod', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 11},
    {"name": 'Butterfree', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 12},
    {"name": 'Weedle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Poison',"dex_number": 13},
    {"name": 'Kakuna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Poison',"dex_number": 14},
    {"name": 'Beedrill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Poison',"dex_number": 15},
    {"name": 'Pidgey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 16},
    {"name": 'Pidgeotto', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"type_2": 'Flying',"dex_number": 17},
    {"name": 'Pidgeot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 18},
    {"name": 'Rattata', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 19},
    {"name": 'Raticate', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Normal',"dex_number": 20},
    {"name": 'Spearow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 21},
    {"name": 'Fearow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"type_2": 'Flying',"dex_number": 22},
    {"name": 'Ekans', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Poison',"dex_number": 23},
    {"name": 'Arbok', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"dex_number": 24},
    {"name": 'Pikachu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 25},
    {"name": 'Raichu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Electric',"dex_number": 26},
    {"name": 'Sandshrew', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ground',"dex_number": 27},
    {"name": 'Sandslash', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"dex_number": 28},
    {"name": 'Nidoran♀', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Poison',"dex_number": 29},
    {"name": 'Nidorina', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Poison',"dex_number": 30},
    {"name": 'Nidoqueen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"type_2": 'Ground',"dex_number": 31},
    {"name": 'Nidoran♂', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Poison',"dex_number": 32},
    {"name": 'Nidorino', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Poison',"dex_number": 33},
    {"name": 'Nidoking', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"type_2": 'Ground',"dex_number": 34},
    {"name": 'Clefairy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Fairy',"dex_number": 35},
    {"name": 'Clefable', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Fairy',"dex_number": 36},
    {"name": 'Vulpix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"dex_number": 37},
    {"name": 'Ninetales', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fire',"dex_number": 38},
    {"name": 'Jigglypuff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 170,"type":'Normal',"type_2": 'Fairy',"dex_number": 39},
    {"name": 'Wigglytuff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Normal',"type_2": 'Fairy',"dex_number": 40},
    {"name": 'Zubat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Poison',"type_2": 'Flying',"dex_number": 41},
    {"name": 'Golbat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"type_2": 'Flying',"dex_number": 42},
    {"name": 'Oddish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Poison',"dex_number": 43},
    {"name": 'Gloom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Poison',"dex_number": 44},
    {"name": 'Vileplume', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Poison',"dex_number": 45},
    {"name": 'Paras', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Grass',"dex_number": 46},
    {"name": 'Parasect', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Grass',"dex_number": 47},
    {"name": 'Venonat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Poison',"dex_number": 48},
    {"name": 'Venomoth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Poison',"dex_number": 49},
    {"name": 'Diglett', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ground',"dex_number": 50},
    {"name": 'Dugtrio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Ground',"dex_number": 51},
    {"name": 'Meowth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 52},
    {"name": 'Persian', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"dex_number": 53},
    {"name": 'Psyduck', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 54},
    {"name": 'Golduck', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 55},
    {"name": 'Mankey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fighting',"dex_number": 56},
    {"name": 'Primeape', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fighting',"dex_number": 57},
    {"name": 'Growlithe', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"dex_number": 58},
    {"name": 'Arcanine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fire',"dex_number": 59},
    {"name": 'Poliwag', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 60},
    {"name": 'Poliwhirl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Water',"dex_number": 61},
    {"name": 'Poliwrath', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Fighting',"dex_number": 62},
    {"name": 'Abra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Psychic',"dex_number": 63},
    {"name": 'Kadabra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Psychic',"dex_number": 64},
    {"name": 'Alakazam', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Psychic',"dex_number": 65},
    {"name": 'Machop', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"dex_number": 66},
    {"name": 'Machoke', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fighting',"dex_number": 67},
    {"name": 'Machamp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 68},
    {"name": 'Bellsprout', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Poison',"dex_number": 69},
    {"name": 'Weepinbell', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Poison',"dex_number": 70},
    {"name": 'Victreebel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Poison',"dex_number": 71},
    {"name": 'Tentacool', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Poison',"dex_number": 72},
    {"name": 'Tentacruel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Poison',"dex_number": 73},
    {"name": 'Geodude', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"type_2": 'Ground',"dex_number": 74},
    {"name": 'Graveler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"type_2": 'Ground',"dex_number": 75},
    {"name": 'Golem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ground',"dex_number": 76},
    {"name": 'Ponyta', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"dex_number": 77},
    {"name": 'Rapidash', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Fire',"dex_number": 78},
    {"name": 'Slowpoke', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Psychic',"dex_number": 79},
    {"name": 'Slowbro', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Psychic',"dex_number": 80},
    {"name": 'Magnemite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"type_2": 'Steel',"dex_number": 81},
    {"name": 'Magneton', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Electric',"type_2": 'Steel',"dex_number": 82},
    {"name": 'Farfetchd', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 83},
    {"name": 'Doduo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"type_2": 'Flying',"dex_number": 84},
    {"name": 'Dodrio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 85},
    {"name": 'Seel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 86},
    {"name": 'Dewgong', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Ice',"dex_number": 87},
    {"name": 'Grimer', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Poison',"dex_number": 88},
    {"name": 'Muk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Poison',"dex_number": 89},
    {"name": 'Shellder', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 90},
    {"name": 'Cloyster', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Ice',"dex_number": 91},
    {"name": 'Gastly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ghost',"type_2": 'Poison',"dex_number": 92},
    {"name": 'Haunter', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ghost',"type_2": 'Poison',"dex_number": 93},
    {"name": 'Gengar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"type_2": 'Poison',"dex_number": 94},
    {"name": 'Onix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ground',"dex_number": 95},
    {"name": 'Drowzee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Psychic',"dex_number": 96},
    {"name": 'Hypno', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Psychic',"dex_number": 97},
    {"name": 'Krabby', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 98},
    {"name": 'Kingler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 99},
    {"name": 'Voltorb', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 100},
    {"name": 'Electrode', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Electric',"dex_number": 101},
    {"name": 'Exeggcute', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Grass',"type_2": 'Psychic',"dex_number": 102},
    {"name": 'Exeggutor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Psychic',"dex_number": 103},
    {"name": 'Cubone', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ground',"dex_number": 104},
    {"name": 'Marowak', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ground',"dex_number": 105},
    {"name": 'Hitmonlee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 106},
    {"name": 'Hitmonchan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 107},
    {"name": 'Lickitung', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 108},
    {"name": 'Koffing', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Poison',"dex_number": 109},
    {"name": 'Weezing', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Poison',"dex_number": 110},
    {"name": 'Rhyhorn', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ground',"type_2": 'Rock',"dex_number": 111},
    {"name": 'Rhydon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"type_2": 'Rock',"dex_number": 112},
    {"name": 'Chansey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Normal',"dex_number": 113},
    {"name": 'Tangela', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 114},
    {"name": 'Kangaskhan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 115},
    {"name": 'Horsea', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 116},
    {"name": 'Seadra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 117},
    {"name": 'Goldeen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 118},
    {"name": 'Seaking', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 119},
    {"name": 'Staryu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 120},
    {"name": 'Starmie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Psychic',"dex_number": 121},
    {"name": 'Mr. Mime', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Fairy',"dex_number": 122},
    {"name": 'Scyther', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 123},
    {"name": 'Jynx', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"type_2": 'Psychic',"dex_number": 124},
    {"name": 'Electabuzz', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 125},
    {"name": 'Magmar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 126},
    {"name": 'Pinsir', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"dex_number": 127},
    {"name": 'Tauros', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 128},
    {"name": 'Magikarp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 129},
    {"name": 'Gyarados', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Flying',"dex_number": 130},
    {"name": 'Lapras', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ice',"dex_number": 131},
    {"name": 'Ditto', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 35,"type":'Normal',"dex_number": 132},
    {"name": 'Eevee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 133},
    {"name": 'Vaporeon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 134},
    {"name": 'Jolteon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 135},
    {"name": 'Flareon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 136},
    {"name": 'Porygon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 137},
    {"name": 'Omanyte', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Water',"dex_number": 138},
    {"name": 'Omastar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Water',"dex_number": 139},
    {"name": 'Kabuto', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Water',"dex_number": 140},
    {"name": 'Kabutops', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Water',"dex_number": 141},
    {"name": 'Aerodactyl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Flying',"dex_number": 142},
    {"name": 'Snorlax', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Normal',"dex_number": 143},
    {"name": 'Articuno', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ice',"type_2": 'Flying',"dex_number": 144},
    {"name": 'Zapdos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"type_2": 'Flying',"dex_number": 145},
    {"name": 'Moltres', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fire',"type_2": 'Flying',"dex_number": 146},
    {"name": 'Dratini', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 147},
    {"name": 'Dragonair', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 148},
    {"name": 'Dragonite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Flying',"dex_number": 149},
    {"name": 'Mewtwo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Psychic',"dex_number": 150},
    {"name": 'Mew', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"dex_number": 151},
    {"name": 'Chikorita', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 152},
    {"name": 'Bayleef', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 153},
    {"name": 'Meganium', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 154},
    {"name": 'Cyndaquil', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 155},
    {"name": 'Quilava', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 156},
    {"name": 'Typhlosion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 157},
    {"name": 'Totodile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 158},
    {"name": 'Croconaw', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 159},
    {"name": 'Feraligatr', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 160},
    {"name": 'Sentret', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 161},
    {"name": 'Furret', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"dex_number": 162},
    {"name": 'Hoothoot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 163},
    {"name": 'Noctowl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"type_2": 'Flying',"dex_number": 164},
    {"name": 'Ledyba', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Flying',"dex_number": 165},
    {"name": 'Ledian', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Bug',"type_2": 'Flying',"dex_number": 166},
    {"name": 'Spinarak', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Poison',"dex_number": 167},
    {"name": 'Ariados', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Bug',"type_2": 'Poison',"dex_number": 168},
    {"name": 'Crobat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"type_2": 'Flying',"dex_number": 169},
    {"name": 'Chinchou', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Electric',"dex_number": 170},
    {"name": 'Lanturn', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Electric',"dex_number": 171},
    {"name": 'Pichu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 172},
    {"name": 'Cleffa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Fairy',"dex_number": 173},
    {"name": 'Igglybuff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 170,"type":'Normal',"type_2": 'Fairy',"dex_number": 174},
    {"name": 'Togepi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fairy',"dex_number": 175},
    {"name": 'Togetic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fairy',"type_2": 'Flying',"dex_number": 176},
    {"name": 'Natu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Psychic',"type_2": 'Flying',"dex_number": 177},
    {"name": 'Xatu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Psychic',"type_2": 'Flying',"dex_number": 178},
    {"name": 'Mareep', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Electric',"dex_number": 179},
    {"name": 'Flaaffy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Electric',"dex_number": 180},
    {"name": 'Ampharos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 181},
    {"name": 'Bellossom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 182},
    {"name": 'Marill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Fairy',"dex_number": 183},
    {"name": 'Azumarill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Fairy',"dex_number": 184},
    {"name": 'Sudowoodo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 65,"type":'Rock',"dex_number": 185},
    {"name": 'Politoed', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 186},
    {"name": 'Hoppip', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Flying',"dex_number": 187},
    {"name": 'Skiploom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Flying',"dex_number": 188},
    {"name": 'Jumpluff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Flying',"dex_number": 189},
    {"name": 'Aipom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 190},
    {"name": 'Sunkern', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Grass',"dex_number": 191},
    {"name": 'Sunflora', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"dex_number": 192},
    {"name": 'Yanma', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Flying',"dex_number": 193},
    {"name": 'Wooper', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"type_2": 'Ground',"dex_number": 194},
    {"name": 'Quagsire', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Water',"type_2": 'Ground',"dex_number": 195},
    {"name": 'Espeon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"dex_number": 196},
    {"name": 'Umbreon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"dex_number": 197},
    {"name": 'Murkrow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Dark',"type_2": 'Flying',"dex_number": 198},
    {"name": 'Slowking', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 70,"type":'Water',"type_2": 'Psychic',"dex_number": 199},
    {"name": 'Misdreavus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"dex_number": 200},
    {"name": 'Unown', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Psychic',"dex_number": 201},
    {"name": 'Wobbuffet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"dex_number": 202},
    {"name": 'Girafarig', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"type_2": 'Psychic',"dex_number": 203},
    {"name": 'Pineco', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"dex_number": 204},
    {"name": 'Forretress', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Steel',"dex_number": 205},
    {"name": 'Dunsparce', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"dex_number": 206},
    {"name": 'Gligar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"type_2": 'Flying',"dex_number": 207},
    {"name": 'Steelix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Steel',"type_2": 'Ground',"dex_number": 208},
    {"name": 'Snubbull', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fairy',"dex_number": 209},
    {"name": 'Granbull', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fairy',"dex_number": 210},
    {"name": 'Qwilfish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Poison',"dex_number": 211},
    {"name": 'Scizor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Bug',"type_2": 'Steel',"dex_number": 212},
    {"name": 'Shuckle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Rock',"dex_number": 213},
    {"name": 'Heracross', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Fighting',"dex_number": 214},
    {"name": 'Sneasel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Dark',"type_2": 'Ice',"dex_number": 215},
    {"name": 'Teddiursa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"dex_number": 216},
    {"name": 'Ursaring', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"dex_number": 217},
    {"name": 'Slugma', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"dex_number": 218},
    {"name": 'Magcargo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fire',"type_2": 'Rock',"dex_number": 219},
    {"name": 'Swinub', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Ice',"type_2": 'Ground',"dex_number": 220},
    {"name": 'Piloswine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ice',"type_2": 'Ground',"dex_number": 221},
    {"name": 'Corsola', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Rock',"dex_number": 222},
    {"name": 'Remoraid', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 223},
    {"name": 'Octillery', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 224},
    {"name": 'Delibird', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"type_2": 'Flying',"dex_number": 225},
    {"name": 'Mantine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Water',"type_2": 'Flying',"dex_number": 226},
    {"name": 'Skarmory', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Steel',"type_2": 'Flying',"dex_number": 227},
    {"name": 'Houndour', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Dark',"type_2": 'Fire',"dex_number": 228},
    {"name": 'Houndoom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Fire',"dex_number": 229},
    {"name": 'Kingdra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Dragon',"dex_number": 230},
    {"name": 'Phanpy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ground',"dex_number": 231},
    {"name": 'Donphan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"dex_number": 232},
    {"name": 'Porygon2', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 233},
    {"name": 'Stantler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 234},
    {"name": 'Smeargle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 235},
    {"name": 'Tyrogue', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fighting',"dex_number": 236},
    {"name": 'Hitmontop', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 237},
    {"name": 'Smoochum', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"type_2": 'Psychic',"dex_number": 238},
    {"name": 'Elekid', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 239},
    {"name": 'Magby', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 240},
    {"name": 'Miltank', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 241},
    {"name": 'Blissey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Normal',"dex_number": 242},
    {"name": 'Raikou', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"dex_number": 243},
    {"name": 'Entei', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fire',"dex_number": 244},
    {"name": 'Suicune', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"dex_number": 245},
    {"name": 'Larvitar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ground',"dex_number": 246},
    {"name": 'Pupitar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ground',"dex_number": 247},
    {"name": 'Tyranitar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Dark',"dex_number": 248},
    {"name": 'Lugia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Flying',"dex_number": 249},
    {"name": 'Ho-Oh', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fire',"type_2": 'Flying',"dex_number": 250},
    {"name": 'Celebi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Grass',"dex_number": 251},
    {"name": 'Treecko', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 252},
    {"name": 'Grovyle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 253},
    {"name": 'Sceptile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 254},
    {"name": 'Torchic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 255},
    {"name": 'Combusken', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 256},
    {"name": 'Blaziken', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 257},
    {"name": 'Mudkip', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 258},
    {"name": 'Marshtomp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ground',"dex_number": 259},
    {"name": 'Swampert', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ground',"dex_number": 260},
    {"name": 'Poochyena', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Dark',"dex_number": 261},
    {"name": 'Mightyena', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Dark',"dex_number": 262},
    {"name": 'Zigzagoon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 263},
    {"name": 'Linoone', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"dex_number": 264},
    {"name": 'Wurmple', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 265},
    {"name": 'Silcoon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 266},
    {"name": 'Beautifly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 267},
    {"name": 'Cascoon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 268},
    {"name": 'Dustox', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Poison',"dex_number": 269},
    {"name": 'Lotad', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"type_2": 'Grass',"dex_number": 270},
    {"name": 'Lombre', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Water',"type_2": 'Grass',"dex_number": 271},
    {"name": 'Ludicolo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Grass',"dex_number": 272},
    {"name": 'Seedot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"dex_number": 273},
    {"name": 'Nuzleaf', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Dark',"dex_number": 274},
    {"name": 'Shiftry', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Dark',"dex_number": 275},
    {"name": 'Taillow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Normal',"type_2": 'Flying',"dex_number": 276},
    {"name": 'Swellow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 277},
    {"name": 'Wingull', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Flying',"dex_number": 278},
    {"name": 'Pelipper', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Flying',"dex_number": 279},
    {"name": 'Ralts', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Psychic',"type_2": 'Fairy',"dex_number": 280},
    {"name": 'Kirlia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Psychic',"type_2": 'Fairy',"dex_number": 281},
    {"name": 'Gardevoir', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Fairy',"dex_number": 282},
    {"name": 'Surskit', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Bug',"type_2": 'Water',"dex_number": 283},
    {"name": 'Masquerain', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Flying',"dex_number": 284},
    {"name": 'Shroomish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"dex_number": 285},
    {"name": 'Breloom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Grass',"type_2": 'Fighting',"dex_number": 286},
    {"name": 'Slakoth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 287},
    {"name": 'Vigoroth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"dex_number": 288},
    {"name": 'Slaking', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 289},
    {"name": 'Nincada', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Ground',"dex_number": 290},
    {"name": 'Ninjask', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Flying',"dex_number": 291},
    {"name": 'Shedinja', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Ghost',"dex_number": 292},
    {"name": 'Whismur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"dex_number": 293},
    {"name": 'Loudred', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"dex_number": 294},
    {"name": 'Exploud', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 295},
    {"name": 'Makuhita', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"dex_number": 296},
    {"name": 'Hariyama', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Fighting',"dex_number": 297},
    {"name": 'Azurill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Normal',"type_2": 'Fairy',"dex_number": 298},
    {"name": 'Nosepass', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"dex_number": 299},
    {"name": 'Skitty', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 300},
    {"name": 'Delcatty', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"dex_number": 301},
    {"name": 'Sableye', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Ghost',"dex_number": 302},
    {"name": 'Mawile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Fairy',"dex_number": 303},
    {"name": 'Aron', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Steel',"type_2": 'Rock',"dex_number": 304},
    {"name": 'Lairon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Steel',"type_2": 'Rock',"dex_number": 305},
    {"name": 'Aggron', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Rock',"dex_number": 306},
    {"name": 'Meditite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"type_2": 'Psychic',"dex_number": 307},
    {"name": 'Medicham', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fighting',"type_2": 'Psychic',"dex_number": 308},
    {"name": 'Electrike', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Electric',"dex_number": 309},
    {"name": 'Manectric', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 310},
    {"name": 'Plusle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Electric',"dex_number": 311},
    {"name": 'Minun', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Electric',"dex_number": 312},
    {"name": 'Volbeat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Bug',"dex_number": 313},
    {"name": 'Illumise', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Bug',"dex_number": 314},
    {"name": 'Roselia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Grass',"type_2": 'Poison',"dex_number": 315},
    {"name": 'Gulpin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Poison',"dex_number": 316},
    {"name": 'Swalot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Poison',"dex_number": 317},
    {"name": 'Carvanha', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"type_2": 'Dark',"dex_number": 318},
    {"name": 'Sharpedo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Dark',"dex_number": 319},
    {"name": 'Wailmer', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 125,"type":'Water',"dex_number": 320},
    {"name": 'Wailord', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 321},
    {"name": 'Numel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Fire',"type_2": 'Ground',"dex_number": 322},
    {"name": 'Camerupt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Fire',"type_2": 'Ground',"dex_number": 323},
    {"name": 'Torkoal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fire',"dex_number": 324},
    {"name": 'Spoink', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Psychic',"dex_number": 325},
    {"name": 'Grumpig', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Psychic',"dex_number": 326},
    {"name": 'Spinda', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 327},
    {"name": 'Trapinch', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ground',"dex_number": 328},
    {"name": 'Vibrava', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ground',"type_2": 'Dragon',"dex_number": 329},
    {"name": 'Flygon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ground',"type_2": 'Dragon',"dex_number": 330},
    {"name": 'Cacnea', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 331},
    {"name": 'Cacturne', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Grass',"type_2": 'Dark',"dex_number": 332},
    {"name": 'Swablu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 333},
    {"name": 'Altaria', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Flying',"dex_number": 334},
    {"name": 'Zangoose', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"dex_number": 335},
    {"name": 'Seviper', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"dex_number": 336},
    {"name": 'Lunatone', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Psychic',"dex_number": 337},
    {"name": 'Solrock', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Psychic',"dex_number": 338},
    {"name": 'Barboach', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Ground',"dex_number": 339},
    {"name": 'Whiscash', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Ground',"dex_number": 340},
    {"name": 'Corphish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 205,"type":'Water',"dex_number": 341},
    {"name": 'Crawdaunt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 155,"type":'Water',"type_2": 'Dark',"dex_number": 342},
    {"name": 'Baltoy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ground',"type_2": 'Psychic',"dex_number": 343},
    {"name": 'Claydol', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"type_2": 'Psychic',"dex_number": 344},
    {"name": 'Lileep', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Grass',"dex_number": 345},
    {"name": 'Cradily', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Grass',"dex_number": 346},
    {"name": 'Anorith', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Bug',"dex_number": 347},
    {"name": 'Armaldo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Bug',"dex_number": 348},
    {"name": 'Feebas', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 349},
    {"name": 'Milotic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 350},
    {"name": 'Castform', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Fire',"dex_number": 351},
    {"name": 'Kecleon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Normal',"dex_number": 352},
    {"name": 'Shuppet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Ghost',"dex_number": 353},
    {"name": 'Banette', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"dex_number": 354},
    {"name": 'Duskull', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ghost',"dex_number": 355},
    {"name": 'Dusclops', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ghost',"dex_number": 356},
    {"name": 'Tropius', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Grass',"type_2": 'Flying',"dex_number": 357},
    {"name": 'Chimecho', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"dex_number": 358},
    {"name": 'Absol', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Dark',"dex_number": 359},
    {"name": 'Wynaut', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 125,"type":'Psychic',"dex_number": 360},
    {"name": 'Snorunt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ice',"dex_number": 361},
    {"name": 'Glalie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ice',"dex_number": 362},
    {"name": 'Spheal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ice',"type_2": 'Water',"dex_number": 363},
    {"name": 'Sealeo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ice',"type_2": 'Water',"dex_number": 364},
    {"name": 'Walrein', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"type_2": 'Water',"dex_number": 365},
    {"name": 'Clamperl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 366},
    {"name": 'Huntail', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 367},
    {"name": 'Gorebyss', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 368},
    {"name": 'Relicanth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Water',"type_2": 'Rock',"dex_number": 369},
    {"name": 'Luvdisc', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 370},
    {"name": 'Bagon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 371},
    {"name": 'Shelgon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 372},
    {"name": 'Salamence', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Flying',"dex_number": 373},
    {"name": 'Beldum', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Psychic',"dex_number": 374},
    {"name": 'Metang', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Psychic',"dex_number": 375},
    {"name": 'Metagross', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Psychic',"dex_number": 376},
    {"name": 'Regirock', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Rock',"dex_number": 377},
    {"name": 'Regice', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ice',"dex_number": 378},
    {"name": 'Registeel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"dex_number": 379},
    {"name": 'Latias', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Psychic',"dex_number": 380},
    {"name": 'Latios', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Psychic',"dex_number": 381},
    {"name": 'Kyogre', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"dex_number": 382},
    {"name": 'Groudon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ground',"type_2": 'Ground',"dex_number": 383},
    {"name": 'Rayquaza', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Flying',"dex_number": 384},
    {"name": 'Jirachi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Psychic',"dex_number": 385},
    {"name": 'Deoxys', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 386},
    {"name": 'Turtwig', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 387},
    {"name": 'Grotle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 388},
    {"name": 'Torterra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Ground',"dex_number": 389},
    {"name": 'Chimchar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 390},
    {"name": 'Monferno', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 391},
    {"name": 'Infernape', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 392},
    {"name": 'Piplup', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 393},
    {"name": 'Prinplup', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 394},
    {"name": 'Empoleon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Steel',"dex_number": 395},
    {"name": 'Starly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 396},
    {"name": 'Staravia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"type_2": 'Flying',"dex_number": 397},
    {"name": 'Staraptor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 398},
    {"name": 'Bidoof', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 399},
    {"name": 'Bibarel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Normal',"type_2": 'Water',"dex_number": 400},
    {"name": 'Kricketot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 401},
    {"name": 'Kricketune', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"dex_number": 402},
    {"name": 'Shinx', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Electric',"dex_number": 403},
    {"name": 'Luxio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Electric',"dex_number": 404},
    {"name": 'Luxray', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 405},
    {"name": 'Budew', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Poison',"dex_number": 406},
    {"name": 'Roserade', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"type_2": 'Poison',"dex_number": 407},
    {"name": 'Cranidos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"dex_number": 408},
    {"name": 'Rampardos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"dex_number": 409},
    {"name": 'Shieldon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Steel',"dex_number": 410},
    {"name": 'Bastiodon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Steel',"dex_number": 411},
    {"name": 'Burmy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 412},
    {"name": 'Wormadam', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Grass',"dex_number": 413},
    {"name": 'Mothim', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 414},
    {"name": 'Combee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Flying',"dex_number": 415},
    {"name": 'Vespiquen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 416},
    {"name": 'Pachirisu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Electric',"dex_number": 417},
    {"name": 'Buizel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 418},
    {"name": 'Floatzel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 419},
    {"name": 'Cherubi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 420},
    {"name": 'Cherrim', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"dex_number": 421},
    {"name": 'Shellos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 422},
    {"name": 'Gastrodon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Ground',"dex_number": 423},
    {"name": 'Ambipom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 424},
    {"name": 'Drifloon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 125,"type":'Ghost',"type_2": 'Flying',"dex_number": 425},
    {"name": 'Drifblim', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"type_2": 'Flying',"dex_number": 426},
    {"name": 'Buneary', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"dex_number": 427},
    {"name": 'Lopunny', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"type_2": 'Normal',"dex_number": 428},
    {"name": 'Mismagius', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"dex_number": 429},
    {"name": 'Honchkrow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Dark',"type_2": 'Flying',"dex_number": 430},
    {"name": 'Glameow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"dex_number": 431},
    {"name": 'Purugly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Normal',"dex_number": 432},
    {"name": 'Chingling', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Psychic',"dex_number": 433},
    {"name": 'Stunky', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Poison',"type_2": 'Dark',"dex_number": 434},
    {"name": 'Skuntank', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Poison',"type_2": 'Dark',"dex_number": 435},
    {"name": 'Bronzor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Steel',"type_2": 'Psychic',"dex_number": 436},
    {"name": 'Bronzong', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Steel',"type_2": 'Psychic',"dex_number": 437},
    {"name": 'Bonsly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"dex_number": 438},
    {"name": 'Mime Jr.', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 145,"type":'Psychic',"type_2": 'Fairy',"dex_number": 439},
    {"name": 'Happiny', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 130,"type":'Normal',"dex_number": 440},
    {"name": 'Chatot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Normal',"type_2": 'Flying',"dex_number": 441},
    {"name": 'Spiritomb', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Ghost',"type_2": 'Dark',"dex_number": 442},
    {"name": 'Gible', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ground',"dex_number": 443},
    {"name": 'Gabite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ground',"dex_number": 444},
    {"name": 'Garchomp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ground',"dex_number": 445},
    {"name": 'Munchlax', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Normal',"dex_number": 446},
    {"name": 'Riolu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fighting',"dex_number": 447},
    {"name": 'Lucario', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"type_2": 'Steel',"dex_number": 448},
    {"name": 'Hippopotas', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Ground',"dex_number": 449},
    {"name": 'Hippowdon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"dex_number": 450},
    {"name": 'Skorupi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Poison',"type_2": 'Bug',"dex_number": 451},
    {"name": 'Drapion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"type_2": 'Dark',"dex_number": 452},
    {"name": 'Croagunk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Poison',"type_2": 'Fighting',"dex_number": 453},
    {"name": 'Toxicroak', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Poison',"type_2": 'Fighting',"dex_number": 454},
    {"name": 'Carnivine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Grass',"dex_number": 455},
    {"name": 'Finneon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 456},
    {"name": 'Lumineon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 457},
    {"name": 'Mantyke', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Water',"type_2": 'Flying',"dex_number": 458},
    {"name": 'Snover', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Ice',"dex_number": 459},
    {"name": 'Abomasnow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Grass',"type_2": 'Ice',"dex_number": 460},
    {"name": 'Weavile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Ice',"dex_number": 461},
    {"name": 'Magnezone', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Electric',"type_2": 'Steel',"dex_number": 462},
    {"name": 'Lickilicky', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Normal',"dex_number": 463},
    {"name": 'Rhyperior', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ground',"type_2": 'Rock',"dex_number": 464},
    {"name": 'Tangrowth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Grass',"dex_number": 465},
    {"name": 'Electivire', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Electric',"dex_number": 466},
    {"name": 'Magmortar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Fire',"dex_number": 467},
    {"name": 'Togekiss', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Fairy',"type_2": 'Flying',"dex_number": 468},
    {"name": 'Yanmega', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Bug',"type_2": 'Flying',"dex_number": 469},
    {"name": 'Leafeon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 470},
    {"name": 'Glaceon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"dex_number": 471},
    {"name": 'Gliscor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ground',"type_2": 'Flying',"dex_number": 472},
    {"name": 'Mamoswine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Ice',"type_2": 'Ground',"dex_number": 473},
    {"name": 'Porygon-Z', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Normal',"dex_number": 474},
    {"name": 'Gallade', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Fighting',"dex_number": 475},
    {"name": 'Probopass', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Rock',"type_2": 'Steel',"dex_number": 476},
    {"name": 'Dusknoir', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"dex_number": 477},
    {"name": 'Froslass', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ice',"type_2": 'Ghost',"dex_number": 478},
    {"name": 'Rotom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"type_2": 'Ghost',"dex_number": 479},
    {"name": 'Uxie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 480},
    {"name": 'Mesprit', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 481},
    {"name": 'Azelf', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 482},
    {"name": 'Dialga', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Dragon',"dex_number": 483},
    {"name": 'Palkia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"type_2": 'Dragon',"dex_number": 484},
    {"name": 'Heatran', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fire',"type_2": 'Steel',"dex_number": 485},
    {"name": 'Regigigas', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Normal',"dex_number": 486},
    {"name": 'Giratina', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ghost',"type_2": 'Dragon',"dex_number": 487},
    {"name": 'Cresselia', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 488},
    {"name": 'Phione', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Water',"dex_number": 489},
    {"name": 'Manaphy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"dex_number": 490},
    {"name": 'Darkrai', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dark',"dex_number": 491},
    {"name": 'Shaymin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Grass',"dex_number": 492},
    {"name": 'Arceus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Normal',"dex_number": 493},
    {"name": 'Victini', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Fire',"dex_number": 494},
    {"name": 'Snivy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 495},
    {"name": 'Servine', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 496},
    {"name": 'Serperior', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 497},
    {"name": 'Tepig', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 498},
    {"name": 'Pignite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 499},
    {"name": 'Emboar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Fighting',"dex_number": 500},
    {"name": 'Oshawott', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 501},
    {"name": 'Dewott', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 502},
    {"name": 'Samurott', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 503},
    {"name": 'Patrat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 504},
    {"name": 'Watchog', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 505},
    {"name": 'Lillipup', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 506},
    {"name": 'Herdier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"dex_number": 507},
    {"name": 'Stoutland', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 508},
    {"name": 'Purrloin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Dark',"dex_number": 509},
    {"name": 'Liepard', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Dark',"dex_number": 510},
    {"name": 'Pansage', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 511},
    {"name": 'Simisage', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"dex_number": 512},
    {"name": 'Pansear', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"dex_number": 513},
    {"name": 'Simisear', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fire',"dex_number": 514},
    {"name": 'Panpour', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 515},
    {"name": 'Simipour', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 516},
    {"name": 'Munna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Psychic',"dex_number": 517},
    {"name": 'Musharna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Psychic',"dex_number": 518},
    {"name": 'Pidove', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 519},
    {"name": 'Tranquill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"type_2": 'Flying',"dex_number": 520},
    {"name": 'Unfezant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 521},
    {"name": 'Blitzle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 522},
    {"name": 'Zebstrika', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Electric',"dex_number": 523},
    {"name": 'Roggenrola', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"dex_number": 524},
    {"name": 'Boldore', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"dex_number": 525},
    {"name": 'Gigalith', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"dex_number": 526},
    {"name": 'Woobat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Psychic',"type_2": 'Flying',"dex_number": 527},
    {"name": 'Swoobat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Flying',"dex_number": 528},
    {"name": 'Drilbur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ground',"dex_number": 529},
    {"name": 'Excadrill', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"type_2": 'Steel',"dex_number": 530},
    {"name": 'Audino', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 531},
    {"name": 'Timburr', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"dex_number": 532},
    {"name": 'Gurdurr', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fighting',"dex_number": 533},
    {"name": 'Conkeldurr', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 534},
    {"name": 'Tympole', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 535},
    {"name": 'Palpitoad', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Water',"type_2": 'Ground',"dex_number": 536},
    {"name": 'Seismitoad', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ground',"dex_number": 537},
    {"name": 'Throh', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 538},
    {"name": 'Sawk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 539},
    {"name": 'Sewaddle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Grass',"dex_number": 540},
    {"name": 'Swadloon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Grass',"dex_number": 541},
    {"name": 'Leavanny', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Grass',"dex_number": 542},
    {"name": 'Venipede', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"type_2": 'Poison',"dex_number": 543},
    {"name": 'Whirlipede', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Poison',"dex_number": 544},
    {"name": 'Scolipede', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Poison',"dex_number": 545},
    {"name": 'Cottonee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"type_2": 'Fairy',"dex_number": 546},
    {"name": 'Whimsicott', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"type_2": 'Fairy',"dex_number": 547},
    {"name": 'Petilil', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 548},
    {"name": 'Lilligant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"dex_number": 549},
    {"name": 'Basculin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"dex_number": 550},
    {"name": 'Sandile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Ground',"type_2": 'Dark',"dex_number": 551},
    {"name": 'Krokorok', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"type_2": 'Dark',"dex_number": 552},
    {"name": 'Krookodile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ground',"type_2": 'Dark',"dex_number": 553},
    {"name": 'Darumaka', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Fire',"type_2": 'Ice',"dex_number": 554},
    {"name": 'Darmanitan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Fire',"type_2": 'Ice',"dex_number": 555},
    {"name": 'Maractus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"dex_number": 556},
    {"name": 'Dwebble', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Rock',"dex_number": 557},
    {"name": 'Crustle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Rock',"dex_number": 558},
    {"name": 'Scraggy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Dark',"type_2": 'Fighting',"dex_number": 559},
    {"name": 'Scrafty', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Dark',"type_2": 'Fighting',"dex_number": 560},
    {"name": 'Sigilyph', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Flying',"dex_number": 561},
    {"name": 'Yamask', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ghost',"type_2": 'Ground',"dex_number": 562},
    {"name": 'Cofagrigus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ghost',"dex_number": 563},
    {"name": 'Tirtouga', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Rock',"dex_number": 564},
    {"name": 'Carracosta', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Rock',"dex_number": 565},
    {"name": 'Archen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Flying',"dex_number": 566},
    {"name": 'Archeops', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Flying',"dex_number": 567},
    {"name": 'Trubbish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Poison',"dex_number": 568},
    {"name": 'Garbodor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Poison',"dex_number": 569},
    {"name": 'Zorua', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Dark',"dex_number": 570},
    {"name": 'Zoroark', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"dex_number": 571},
    {"name": 'Minccino', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 572},
    {"name": 'Cinccino', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"dex_number": 573},
    {"name": 'Gothita', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Psychic',"dex_number": 574},
    {"name": 'Gothorita', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Psychic',"dex_number": 575},
    {"name": 'Gothitelle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Psychic',"dex_number": 576},
    {"name": 'Solosis', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Psychic',"dex_number": 577},
    {"name": 'Duosion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Psychic',"dex_number": 578},
    {"name": 'Reuniclus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Psychic',"dex_number": 579},
    {"name": 'Ducklett', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Flying',"dex_number": 580},
    {"name": 'Swanna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Flying',"dex_number": 581},
    {"name": 'Vanillite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ice',"dex_number": 582},
    {"name": 'Vanillish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ice',"dex_number": 583},
    {"name": 'Vanilluxe', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"dex_number": 584},
    {"name": 'Deerling', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"type_2": 'Grass',"dex_number": 585},
    {"name": 'Sawsbuck', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Normal',"type_2": 'Grass',"dex_number": 586},
    {"name": 'Emolga', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Electric',"type_2": 'Flying',"dex_number": 587},
    {"name": 'Karrablast', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Bug',"dex_number": 588},
    {"name": 'Escavalier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Steel',"dex_number": 589},
    {"name": 'Foongus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"type_2": 'Poison',"dex_number": 590},
    {"name": 'Amoonguss', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"type_2": 'Poison',"dex_number": 591},
    {"name": 'Frillish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Water',"type_2": 'Ghost',"dex_number": 592},
    {"name": 'Jellicent', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"type_2": 'Ghost',"dex_number": 593},
    {"name": 'Alomomola', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"dex_number": 594},
    {"name": 'Joltik', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Electric',"dex_number": 595},
    {"name": 'Galvantula', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Electric',"dex_number": 596},
    {"name": 'Ferroseed', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Steel',"dex_number": 597},
    {"name": 'Ferrothorn', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Grass',"type_2": 'Steel',"dex_number": 598},
    {"name": 'Klink', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 130,"type":'Steel',"dex_number": 599},
    {"name": 'Klang', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Steel',"dex_number": 600},
    {"name": 'Klinklang', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Steel',"dex_number": 601},
    {"name": 'Tynamo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 602},
    {"name": 'Eelektrik', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Electric',"dex_number": 603},
    {"name": 'Eelektross', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Electric',"dex_number": 604},
    {"name": 'Elgyem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Psychic',"dex_number": 605},
    {"name": 'Beheeyem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Psychic',"dex_number": 606},
    {"name": 'Litwick', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ghost',"type_2": 'Fire',"dex_number": 607},
    {"name": 'Lampent', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ghost',"type_2": 'Fire',"dex_number": 608},
    {"name": 'Chandelure', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"type_2": 'Fire',"dex_number": 609},
    {"name": 'Axew', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Dragon',"dex_number": 610},
    {"name": 'Fraxure', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Dragon',"dex_number": 611},
    {"name": 'Haxorus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 612},
    {"name": 'Cubchoo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ice',"dex_number": 613},
    {"name": 'Beartic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ice',"dex_number": 614},
    {"name": 'Cryogonal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Ice',"dex_number": 615},
    {"name": 'Shelmet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Bug',"dex_number": 616},
    {"name": 'Accelgor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"dex_number": 617},
    {"name": 'Stunfisk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ground',"type_2": 'Electric',"dex_number": 618},
    {"name": 'Mienfoo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"dex_number": 619},
    {"name": 'Mienshao', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 620},
    {"name": 'Druddigon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 621},
    {"name": 'Golett', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ground',"type_2": 'Ghost',"dex_number": 622},
    {"name": 'Golurk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"type_2": 'Ghost',"dex_number": 623},
    {"name": 'Pawniard', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Dark',"type_2": 'Steel',"dex_number": 624},
    {"name": 'Bisharp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Steel',"dex_number": 625},
    {"name": 'Bouffalant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 626},
    {"name": 'Rufflet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"type_2": 'Flying',"dex_number": 627},
    {"name": 'Braviary', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Normal',"type_2": 'Flying',"dex_number": 628},
    {"name": 'Vullaby', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Dark',"type_2": 'Flying',"dex_number": 629},
    {"name": 'Mandibuzz', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Dark',"type_2": 'Flying',"dex_number": 630},
    {"name": 'Heatmor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fire',"dex_number": 631},
    {"name": 'Durant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Bug',"type_2": 'Steel',"dex_number": 632},
    {"name": 'Deino', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Dragon',"dex_number": 633},
    {"name": 'Zweilous', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Dragon',"dex_number": 634},
    {"name": 'Hydreigon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Dragon',"dex_number": 635},
    {"name": 'Larvesta', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Fire',"dex_number": 636},
    {"name": 'Volcarona', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 15,"type":'Bug',"type_2": 'Fire',"dex_number": 637},
    {"name": 'Cobalion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Fighting',"dex_number": 638},
    {"name": 'Terrakion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Rock',"type_2": 'Fighting',"dex_number": 639},
    {"name": 'Virizion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Grass',"type_2": 'Fighting',"dex_number": 640},
    {"name": 'Tornadus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Flying',"dex_number": 641},
    {"name": 'Thundurus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"type_2": 'Flying',"dex_number": 642},
    {"name": 'Reshiram', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Fire',"dex_number": 643},
    {"name": 'Zekrom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Electric',"dex_number": 644},
    {"name": 'Landorus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ground',"type_2": 'Flying',"dex_number": 645},
    {"name": 'Kyurem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Ice',"dex_number": 646},
    {"name": 'Keldeo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"type_2": 'Fighting',"dex_number": 647},
    {"name": 'Meloetta', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Normal',"type_2": 'Psychic',"dex_number": 648},
    {"name": 'Genesect', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Bug',"type_2": 'Steel',"dex_number": 649},
    {"name": 'Chespin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 650},
    {"name": 'Quilladin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 651},
    {"name": 'Chesnaught', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Fighting',"dex_number": 652},
    {"name": 'Fennekin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 653},
    {"name": 'Braixen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 654},
    {"name": 'Delphox', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Psychic',"dex_number": 655},
    {"name": 'Froakie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 656},
    {"name": 'Frogadier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 657},
    {"name": 'Greninja', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Dark',"dex_number": 658},
    {"name": 'Bunnelby', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 659},
    {"name": 'Diggersby', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Normal',"type_2": 'Ground',"dex_number": 660},
    {"name": 'Fletchling', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 661},
    {"name": 'Fletchinder', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Fire',"type_2": 'Flying',"dex_number": 662},
    {"name": 'Talonflame', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Flying',"dex_number": 663},
    {"name": 'Scatterbug', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 664},
    {"name": 'Spewpa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 665},
    {"name": 'Vivillon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Flying',"dex_number": 666},
    {"name": 'Litleo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 220,"type":'Fire',"type_2": 'Normal',"dex_number": 667},
    {"name": 'Pyroar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 65,"type":'Fire',"type_2": 'Normal',"dex_number": 668},
    {"name": 'Flabébé', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Fairy',"dex_number": 669},
    {"name": 'Floette', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Fairy',"dex_number": 670},
    {"name": 'Florges', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fairy',"dex_number": 671},
    {"name": 'Skiddo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Grass',"dex_number": 672},
    {"name": 'Gogoat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 673},
    {"name": 'Pancham', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 220,"type":'Fighting',"dex_number": 674},
    {"name": 'Pangoro', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 65,"type":'Fighting',"type_2": 'Dark',"dex_number": 675},
    {"name": 'Furfrou', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 160,"type":'Normal',"dex_number": 676},
    {"name": 'Espurr', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Psychic',"dex_number": 677},
    {"name": 'Meowstic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Psychic',"dex_number": 678},
    {"name": 'Honedge', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Steel',"type_2": 'Ghost',"dex_number": 679},
    {"name": 'Doublade', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Steel',"type_2": 'Ghost',"dex_number": 680},
    {"name": 'Aegislash', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Ghost',"dex_number": 681},
    {"name": 'Spritzee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Fairy',"dex_number": 682},
    {"name": 'Aromatisse', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Fairy',"dex_number": 683},
    {"name": 'Swirlix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Fairy',"dex_number": 684},
    {"name": 'Slurpuff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Fairy',"dex_number": 685},
    {"name": 'Inkay', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Dark',"type_2": 'Psychic',"dex_number": 686},
    {"name": 'Malamar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 80,"type":'Dark',"type_2": 'Psychic',"dex_number": 687},
    {"name": 'Binacle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"type_2": 'Water',"dex_number": 688},
    {"name": 'Barbaracle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Water',"dex_number": 689},
    {"name": 'Skrelp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Poison',"type_2": 'Water',"dex_number": 690},
    {"name": 'Dragalge', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 55,"type":'Poison',"type_2": 'Dragon',"dex_number": 691},
    {"name": 'Clauncher', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Water',"dex_number": 692},
    {"name": 'Clawitzer', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 55,"type":'Water',"dex_number": 693},
    {"name": 'Helioptile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"type_2": 'Normal',"dex_number": 694},
    {"name": 'Heliolisk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Electric',"type_2": 'Normal',"dex_number": 695},
    {"name": 'Tyrunt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Dragon',"dex_number": 696},
    {"name": 'Tyrantrum', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Dragon',"dex_number": 697},
    {"name": 'Amaura', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ice',"dex_number": 698},
    {"name": 'Aurorus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Ice',"dex_number": 699},
    {"name": 'Sylveon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fairy',"dex_number": 700},
    {"name": 'Hawlucha', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Fighting',"type_2": 'Flying',"dex_number": 701},
    {"name": 'Dedenne', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Electric',"type_2": 'Fairy',"dex_number": 702},
    {"name": 'Carbink', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Rock',"type_2": 'Fairy',"dex_number": 703},
    {"name": 'Goomy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 704},
    {"name": 'Sliggoo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 705},
    {"name": 'Goodra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 706},
    {"name": 'Klefki', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Steel',"type_2": 'Fairy',"dex_number": 707},
    {"name": 'Phantump', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ghost',"type_2": 'Grass',"dex_number": 708},
    {"name": 'Trevenant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"type_2": 'Grass',"dex_number": 709},
    {"name": 'Pumpkaboo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ghost',"type_2": 'Grass',"dex_number": 710},
    {"name": 'Gourgeist', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"type_2": 'Grass',"dex_number": 711},
    {"name": 'Bergmite', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ice',"dex_number": 712},
    {"name": 'Avalugg', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 55,"type":'Ice',"type_2": 'Ice',"dex_number": 713},
    {"name": 'Noibat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Flying',"type_2": 'Dragon',"dex_number": 714},
    {"name": 'Noivern', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Flying',"type_2": 'Dragon',"dex_number": 715},
    {"name": 'Xerneas', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fairy',"dex_number": 716},
    {"name": 'Yveltal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Flying',"dex_number": 717},
    {"name": 'Zygarde', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"type_2": 'Ground',"dex_number": 718},
    {"name": 'Diancie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Rock',"type_2": 'Fairy',"dex_number": 719},
    {"name": 'Hoopa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Ghost',"dex_number": 720},
    {"name": 'Volcanion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fire',"type_2": 'Water',"dex_number": 721},
    {"name": 'Rowlet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Flying',"dex_number": 722},
    {"name": 'Dartrix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Flying',"dex_number": 723},
    {"name": 'Decidueye', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Ghost',"dex_number": 724},
    {"name": 'Litten', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 725},
    {"name": 'Torracat', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 726},
    {"name": 'Incineroar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Dark',"dex_number": 727},
    {"name": 'Popplio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 728},
    {"name": 'Brionne', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 729},
    {"name": 'Primarina', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Fairy',"dex_number": 730},
    {"name": 'Pikipek', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"type_2": 'Flying',"dex_number": 731},
    {"name": 'Trumbeak', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Normal',"type_2": 'Flying',"dex_number": 732},
    {"name": 'Toucannon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Flying',"dex_number": 733},
    {"name": 'Yungoos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 734},
    {"name": 'Gumshoos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Normal',"dex_number": 735},
    {"name": 'Grubbin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 736},
    {"name": 'Charjabug', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Electric',"dex_number": 737},
    {"name": 'Vikavolt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Electric',"dex_number": 738},
    {"name": 'Crabrawler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 225,"type":'Fighting',"dex_number": 739},
    {"name": 'Crabominable', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Fighting',"type_2": 'Ice',"dex_number": 740},
    {"name": 'Oricorio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Flying',"dex_number": 741},
    {"name": 'Cutiefly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"type_2": 'Fairy',"dex_number": 742},
    {"name": 'Ribombee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Bug',"type_2": 'Fairy',"dex_number": 743},
    {"name": 'Rockruff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Rock',"dex_number": 744},
    {"name": 'Lycanroc', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Rock',"dex_number": 745},
    {"name": 'Wishiwashi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 746},
    {"name": 'Mareanie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Poison',"type_2": 'Water',"dex_number": 747},
    {"name": 'Toxapex', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Poison',"type_2": 'Water',"dex_number": 748},
    {"name": 'Mudbray', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ground',"dex_number": 749},
    {"name": 'Mudsdale', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ground',"dex_number": 750},
    {"name": 'Dewpider', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Water',"type_2": 'Bug',"dex_number": 751},
    {"name": 'Araquanid', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Water',"type_2": 'Bug',"dex_number": 752},
    {"name": 'Fomantis', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 753},
    {"name": 'Lurantis', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"dex_number": 754},
    {"name": 'Morelull', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"type_2": 'Fairy',"dex_number": 755},
    {"name": 'Shiinotic', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"type_2": 'Fairy',"dex_number": 756},
    {"name": 'Salandit', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Poison',"type_2": 'Fire',"dex_number": 757},
    {"name": 'Salazzle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"type_2": 'Fire',"dex_number": 758},
    {"name": 'Stufful', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Normal',"type_2": 'Fighting',"dex_number": 759},
    {"name": 'Bewear', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 70,"type":'Normal',"type_2": 'Fighting',"dex_number": 760},
    {"name": 'Bounsweet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Grass',"dex_number": 761},
    {"name": 'Steenee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"dex_number": 762},
    {"name": 'Tsareena', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 763},
    {"name": 'Comfey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Fairy',"dex_number": 764},
    {"name": 'Oranguru', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Psychic',"dex_number": 765},
    {"name": 'Passimian', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 766},
    {"name": 'Wimpod', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Bug',"type_2": 'Water',"dex_number": 767},
    {"name": 'Golisopod', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Water',"dex_number": 768},
    {"name": 'Sandygast', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 140,"type":'Ghost',"type_2": 'Ground',"dex_number": 769},
    {"name": 'Palossand', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"type_2": 'Ground',"dex_number": 770},
    {"name": 'Pyukumuku', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 771},
    {"name": 'Type: Null', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Normal',"dex_number": 772},
    {"name": 'Silvally', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Normal',"dex_number": 773},
    {"name": 'Minior', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Rock',"type_2": 'Flying',"dex_number": 774},
    {"name": 'Komala', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 775},
    {"name": 'Turtonator', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 70,"type":'Fire',"type_2": 'Dragon',"dex_number": 776},
    {"name": 'Togedemaru', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Electric',"type_2": 'Steel',"dex_number": 777},
    {"name": 'Mimikyu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"type_2": 'Fairy',"dex_number": 778},
    {"name": 'Bruxish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 80,"type":'Water',"type_2": 'Psychic',"dex_number": 779},
    {"name": 'Drampa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 70,"type":'Normal',"type_2": 'Dragon',"dex_number": 780},
    {"name": 'Dhelmise', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Ghost',"type_2": 'Grass',"dex_number": 781},
    {"name": 'Jangmo-o', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"dex_number": 782},
    {"name": 'Hakamo-o', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Fighting',"dex_number": 783},
    {"name": 'Kommo-o', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Fighting',"dex_number": 784},
    {"name": 'Tapu Koko', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"type_2": 'Fairy',"dex_number": 785},
    {"name": 'Tapu Lele', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Fairy',"dex_number": 786},
    {"name": 'Tapu Bulu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Grass',"type_2": 'Fairy',"dex_number": 787},
    {"name": 'Tapu Fini', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Water',"type_2": 'Fairy',"dex_number": 788},
    {"name": 'Cosmog', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 789},
    {"name": 'Cosmoem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"dex_number": 790},
    {"name": 'Solgaleo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Steel',"dex_number": 791},
    {"name": 'Lunala', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Ghost',"dex_number": 792},
    {"name": 'Nihilego', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Poison',"dex_number": 793},
    {"name": 'Buzzwole', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Fighting',"dex_number": 794},
    {"name": 'Pheromosa', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Fighting',"dex_number": 795},
    {"name": 'Xurkitree', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 796},
    {"name": 'Celesteela', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Flying',"dex_number": 797},
    {"name": 'Kartana', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Steel',"dex_number": 798},
    {"name": 'Guzzlord', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Dragon',"dex_number": 799},
    {"name": 'Necrozma', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Psychic',"dex_number": 800},
    {"name": 'Magearna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"type_2": 'Fairy',"dex_number": 801},
    {"name": 'Marshadow', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fighting',"type_2": 'Ghost',"dex_number": 802},
    {"name": 'Poipole', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"dex_number": 803},
    {"name": 'Naganadel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Poison',"type_2": 'Dragon',"dex_number": 804},
    {"name": 'Stakataka', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Rock',"type_2": 'Steel',"dex_number": 805},
    {"name": 'Blacephalon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Fire',"type_2": 'Ghost',"dex_number": 806},
    {"name": 'Zeraora', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"dex_number": 807},
    {"name": 'Meltan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"dex_number": 808},
    {"name": 'Melmetal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Steel',"dex_number": 809},
    {"name": 'Grookey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 810},
    {"name": 'Thwackey', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 811},
    {"name": 'Rillaboom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 812},
    {"name": 'Scorbunny', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 813},
    {"name": 'Raboot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 814},
    {"name": 'Cinderace', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 815},
    {"name": 'Sobble', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 816},
    {"name": 'Drizzile', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 817},
    {"name": 'Inteleon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 818},
    {"name": 'Skwovet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 819},
    {"name": 'Greedent', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Normal',"dex_number": 820},
    {"name": 'Rookidee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Flying',"dex_number": 821},
    {"name": 'Corvisquire', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Flying',"dex_number": 822},
    {"name": 'Corviknight', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Flying',"type_2": 'Steel',"dex_number": 823},
    {"name": 'Blipbug', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 824},
    {"name": 'Dottler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"type_2": 'Psychic',"dex_number": 825},
    {"name": 'Orbeetle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Psychic',"dex_number": 826},
    {"name": 'Nickit', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Dark',"dex_number": 827},
    {"name": 'Thievul', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Dark',"dex_number": 828},
    {"name": 'Gossifleur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 829},
    {"name": 'Eldegoss', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"dex_number": 830},
    {"name": 'Wooloo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 831},
    {"name": 'Dubwool', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 127,"type":'Normal',"dex_number": 832},
    {"name": 'Chewtle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 833},
    {"name": 'Drednaw', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Water',"type_2": 'Rock',"dex_number": 834},
    {"name": 'Yamper', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Electric',"dex_number": 835},
    {"name": 'Boltund', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"dex_number": 836},
    {"name": 'Rolycoly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"dex_number": 837},
    {"name": 'Carkol', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"type_2": 'Fire',"dex_number": 838},
    {"name": 'Coalossal', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"type_2": 'Fire',"dex_number": 839},
    {"name": 'Applin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Dragon',"dex_number": 840},
    {"name": 'Flapple', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Dragon',"dex_number": 841},
    {"name": 'Appletun', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Dragon',"dex_number": 842},
    {"name": 'Silicobra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Ground',"dex_number": 843},
    {"name": 'Sandaconda', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ground',"dex_number": 844},
    {"name": 'Cramorant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Flying',"type_2": 'Water',"dex_number": 845},
    {"name": 'Arrokuda', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 846},
    {"name": 'Barraskewda', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Water',"dex_number": 847},
    {"name": 'Toxel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Electric',"type_2": 'Poison',"dex_number": 848},
    {"name": 'Toxtricity', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"type_2": 'Poison',"dex_number": 849},
    {"name": 'Sizzlipede', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fire',"type_2": 'Bug',"dex_number": 850},
    {"name": 'Centiskorch', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Fire',"type_2": 'Bug',"dex_number": 851},
    {"name": 'Clobbopus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Fighting',"dex_number": 852},
    {"name": 'Grapploct', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 853},
    {"name": 'Sinistea', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ghost',"dex_number": 854},
    {"name": 'Polteageist', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"dex_number": 855},
    {"name": 'Hatenna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 235,"type":'Psychic',"dex_number": 856},
    {"name": 'Hattrem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Psychic',"dex_number": 857},
    {"name": 'Hatterene', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Psychic',"type_2": 'Fairy',"dex_number": 858},
    {"name": 'Impidimp', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Dark',"type_2": 'Fairy',"dex_number": 859},
    {"name": 'Morgrem', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Dark',"type_2": 'Fairy',"dex_number": 860},
    {"name": 'Grimmsnarl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Fairy',"dex_number": 861},
    {"name": 'Obstagoon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Normal',"dex_number": 862},
    {"name": 'Perrserker', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Steel',"dex_number": 863},
    {"name": 'Cursola', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ghost',"dex_number": 864},
    {"name": 'Sirfetchd', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 865},
    {"name": 'Mr. Rime', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ice',"type_2": 'Psychic',"dex_number": 866},
    {"name": 'Runerigus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"type_2": 'Ghost',"dex_number": 867},
    {"name": 'Milcery', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Fairy',"dex_number": 868},
    {"name": 'Alcremie', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Fairy',"dex_number": 869},
    {"name": 'Falinks', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"dex_number": 870},
    {"name": 'Pincurchin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Electric',"dex_number": 871},
    {"name": 'Snom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ice',"type_2": 'Bug',"dex_number": 872},
    {"name": 'Frosmoth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Ice',"type_2": 'Bug',"dex_number": 873},
    {"name": 'Stonjourner', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Rock',"dex_number": 874},
    {"name": 'Eiscue', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ice',"dex_number": 875},
    {"name": 'Indeedee', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Psychic',"type_2": 'Normal',"dex_number": 876},
    {"name": 'Morpeko', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Electric',"type_2": 'Dark',"dex_number": 877},
    {"name": 'Cufant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Steel',"dex_number": 878},
    {"name": 'Copperajah', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Steel',"dex_number": 879},
    {"name": 'Dracozolt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"type_2": 'Dragon',"dex_number": 880},
    {"name": 'Arctozolt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"type_2": 'Ice',"dex_number": 881},
    {"name": 'Dracovish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Dragon',"dex_number": 882},
    {"name": 'Arctovish', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ice',"dex_number": 883},
    {"name": 'Duraludon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Dragon',"dex_number": 884},
    {"name": 'Dreepy', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ghost',"dex_number": 885},
    {"name": 'Drakloak', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ghost',"dex_number": 886},
    {"name": 'Dragapult', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ghost',"dex_number": 887},
    {"name": 'Zacian', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Fairy',"type_2": 'Steel',"dex_number": 888},
    {"name": 'Zamazenta', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Fighting',"type_2": 'Steel',"dex_number": 889},
    {"name": 'Eternatus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Poison',"type_2": 'Dragon',"dex_number": 890},
    {"name": 'Kubfu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fighting',"dex_number": 891},
    {"name": 'Urshifu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fighting',"type_2": 'Dark',"dex_number": 892},
    {"name": 'Zarude', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dark',"type_2": 'Grass',"dex_number": 893},
    {"name": 'Regieleki', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"dex_number": 894},
    {"name": 'Regidrago', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Dragon',"dex_number": 895},
    {"name": 'Glastrier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ice',"dex_number": 896},
    {"name": 'Spectrier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Ghost',"dex_number": 897},
    {"name": 'Calyrex', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Psychic',"type_2": 'Grass',"dex_number": 898},
    {"name": 'Wyrdeer', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Psychic',"dex_number": 899},
    {"name": 'Kleavor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 15,"type":'Bug',"type_2": 'Rock',"dex_number": 900},
    {"name": 'Ursaluna', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 20,"type":'Ground',"type_2": 'Normal',"dex_number": 901},
    {"name": 'Basculegion', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Ghost',"dex_number": 902},
    {"name": 'Sneasler', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 20,"type":'Fighting',"type_2": 'Poison',"dex_number": 903},
    {"name": 'Overqwil', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dark',"type_2": 'Poison',"dex_number": 904},
    {"name": 'Enamorus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fairy',"type_2": 'Flying',"dex_number": 905},
    {"name": 'Sprigatito', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 906},
    {"name": 'Floragato', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"dex_number": 907},
    {"name": 'Meowscarada', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Dark',"dex_number": 908},
    {"name": 'Fuecoco', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 909},
    {"name": 'Crocalor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"dex_number": 910},
    {"name": 'Skeledirge', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fire',"type_2": 'Ghost',"dex_number": 911},
    {"name": 'Quaxly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 912},
    {"name": 'Quaxwell', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 913},
    {"name": 'Quaquaval', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"type_2": 'Fighting',"dex_number": 914},
    {"name": 'Lechonk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 915},
    {"name": 'Oinkologne', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Normal',"dex_number": 916},
    {"name": 'Tarountula', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Bug',"dex_number": 917},
    {"name": 'Spidops', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Bug',"dex_number": 918},
    {"name": 'Nymble', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"dex_number": 919},
    {"name": 'Lokix', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Bug',"type_2": 'Dark',"dex_number": 920},
    {"name": 'Pawmi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 921},
    {"name": 'Pawmo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 80,"type":'Electric',"type_2": 'Fighting',"dex_number": 922},
    {"name": 'Pawmot', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Electric',"type_2": 'Fighting',"dex_number": 923},
    {"name": 'Tandemaus', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Normal',"dex_number": 924},
    {"name": 'Maushold', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Normal',"dex_number": 925},
    {"name": 'Fidough', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fairy',"dex_number": 926},
    {"name": 'Dachsbun', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fairy',"dex_number": 927},
    {"name": 'Smoliv', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Grass',"type_2": 'Normal',"dex_number": 928},
    {"name": 'Dolliv', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Normal',"dex_number": 929},
    {"name": 'Arboliva', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Normal',"dex_number": 930},
    {"name": 'Squawkabilly', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Normal',"type_2": 'Flying',"dex_number": 931},
    {"name": 'Nacli', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Rock',"dex_number": 932},
    {"name": 'Naclstack', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"dex_number": 933},
    {"name": 'Garganacl', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Rock',"dex_number": 934},
    {"name": 'Charcadet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fire',"dex_number": 935},
    {"name": 'Armarouge', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Fire',"type_2": 'Psychic',"dex_number": 936},
    {"name": 'Ceruledge', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Fire',"type_2": 'Ghost',"dex_number": 937},
    {"name": 'Tadbulb', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Electric',"dex_number": 938},
    {"name": 'Bellibolt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Electric',"dex_number": 939},
    {"name": 'Wattrel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 180,"type":'Electric',"type_2": 'Flying',"dex_number": 940},
    {"name": 'Kilowattrel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Electric',"type_2": 'Flying',"dex_number": 941},
    {"name": 'Maschiff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Dark',"dex_number": 942},
    {"name": 'Mabosstiff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Dark',"dex_number": 943},
    {"name": 'Shroodle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Poison',"type_2": 'Normal',"dex_number": 944},
    {"name": 'Grafaiai', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"type_2": 'Normal',"dex_number": 945},
    {"name": 'Bramblin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"type_2": 'Ghost',"dex_number": 946},
    {"name": 'Brambleghast', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Ghost',"dex_number": 947},
    {"name": 'Toedscool', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Ground',"type_2": 'Grass',"dex_number": 948},
    {"name": 'Toedscruel', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Ground',"type_2": 'Grass',"dex_number": 949},
    {"name": 'Klawf', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Rock',"dex_number": 950},
    {"name": 'Capsakid', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Grass',"dex_number": 951},
    {"name": 'Scovillain', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Grass',"type_2": 'Fire',"dex_number": 952},
    {"name": 'Rellor', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Bug',"dex_number": 953},
    {"name": 'Rabsca', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Bug',"type_2": 'Psychic',"dex_number": 954},
    {"name": 'Flittle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Psychic',"dex_number": 955},
    {"name": 'Espathra', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Psychic',"dex_number": 956},
    {"name": 'Tinkatink', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Fairy',"type_2": 'Steel',"dex_number": 957},
    {"name": 'Tinkatuff', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Fairy',"type_2": 'Steel',"dex_number": 958},
    {"name": 'Tinkaton', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fairy',"type_2": 'Steel',"dex_number": 959},
    {"name": 'Wiglett', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Water',"dex_number": 960},
    {"name": 'Wugtrio', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Water',"dex_number": 961},
    {"name": 'Bombirdier', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Flying',"type_2": 'Dark',"dex_number": 962},
    {"name": 'Finizen', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 200,"type":'Water',"dex_number": 963},
    {"name": 'Palafin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Water',"dex_number": 964},
    {"name": 'Varoom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Steel',"type_2": 'Poison',"dex_number": 965},
    {"name": 'Revavroom', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 75,"type":'Steel',"type_2": 'Poison',"dex_number": 966},
    {"name": 'Cyclizar', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 190,"type":'Dragon',"type_2": 'Normal',"dex_number": 967},
    {"name": 'Orthworm', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Steel',"dex_number": 968},
    {"name": 'Glimmet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 70,"type":'Rock',"type_2": 'Poison',"dex_number": 969},
    {"name": 'Glimmora', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Rock',"type_2": 'Poison',"dex_number": 970},
    {"name": 'Greavard', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Ghost',"dex_number": 971},
    {"name": 'Houndstone', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Ghost',"dex_number": 972},
    {"name": 'Flamigo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Flying',"type_2": 'Fighting',"dex_number": 973},
    {"name": 'Cetoddle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 150,"type":'Ice',"dex_number": 974},
    {"name": 'Cetitan', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Ice',"dex_number": 975},
    {"name": 'Veluza', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Water',"type_2": 'Psychic',"dex_number": 976},
    {"name": 'Dondozo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Water',"dex_number": 977},
    {"name": 'Tatsugiri', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 100,"type":'Dragon',"type_2": 'Water',"dex_number": 978},
    {"name": 'Annihilape', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Fighting',"type_2": 'Ghost',"dex_number": 979},
    {"name": 'Clodsire', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 90,"type":'Poison',"type_2": 'Ground',"dex_number": 980},
    {"name": 'Farigiraf', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"type_2": 'Psychic',"dex_number": 981},
    {"name": 'Dudunsparce', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Normal',"dex_number": 982},
    {"name": 'Kingambit', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Dark',"type_2": 'Steel',"dex_number": 983},
    {"name": 'Great Tusk', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ground',"type_2": 'Fighting',"dex_number": 984},
    {"name": 'Scream Tail', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Fairy',"type_2": 'Psychic',"dex_number": 985},
    {"name": 'Brute Bonnet', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Grass',"type_2": 'Dark',"dex_number": 986},
    {"name": 'Flutter Mane', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ghost',"type_2": 'Fairy',"dex_number": 987},
    {"name": 'Slither Wing', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Bug',"type_2": 'Fighting',"dex_number": 988},
    {"name": 'Sandy Shocks', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Electric',"type_2": 'Ground',"dex_number": 989},
    {"name": 'Iron Treads', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Ground',"type_2": 'Steel',"dex_number": 990},
    {"name": 'Iron Bundle', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Ice',"type_2": 'Water',"dex_number": 991},
    {"name": 'Iron Hands', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 50,"type":'Fighting',"type_2": 'Electric',"dex_number": 992},
    {"name": 'Iron Jugulis', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Dark',"type_2": 'Flying',"dex_number": 993},
    {"name": 'Iron Moth', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Fire',"type_2": 'Poison',"dex_number": 994},
    {"name": 'Iron Thorns', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 30,"type":'Rock',"type_2": 'Electric',"dex_number": 995},
    {"name": 'Frigibax', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Dragon',"type_2": 'Ice',"dex_number": 996},
    {"name": 'Arctibax', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 25,"type":'Dragon',"type_2": 'Ice',"dex_number": 997},
    {"name": 'Baxcalibur', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Dragon',"type_2": 'Ice',"dex_number": 998},
    {"name": 'Gimmighoul', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Ghost',"dex_number": 999},
    {"name": 'Gholdengo', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Steel',"type_2": 'Ghost',"dex_number": 1000},
    {"name": 'Wo-Chien', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 6,"type":'Dark',"type_2": 'Grass',"dex_number": 1001},
    {"name": 'Chien-Pao', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 6,"type":'Dark',"type_2": 'Ice',"dex_number": 1002},
    {"name": 'Ting-Lu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 6,"type":'Dark',"type_2": 'Ground',"dex_number": 1003},
    {"name": 'Chi-Yu', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 6,"type":'Dark',"type_2": 'Fire',"dex_number": 1004},
    {"name": 'Roaring Moon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Dragon',"type_2": 'Dark',"dex_number": 1005},
    {"name": 'Iron Valiant', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Fairy',"type_2": 'Fighting',"dex_number": 1006},
    {"name": 'Koraidon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Fighting',"type_2": 'Dragon',"dex_number": 1007},
    {"name": 'Miraidon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Electric',"type_2": 'Dragon',"dex_number": 1008},
    {"name": 'Walking Wake', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 5,"type":'Water',"type_2": 'Dragon',"dex_number": 1009},
    {"name": 'Iron Leaves', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 5,"type":'Grass',"type_2": 'Psychic',"dex_number": 1010},
    {"name": 'Dipplin', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 45,"type":'Grass',"type_2": 'Dragon',"dex_number": 1011},
    {"name": 'Poltchageist', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 120,"type":'Grass',"type_2": 'Ghost',"dex_number": 1012},
    {"name": 'Sinistcha', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 60,"type":'Grass',"type_2": 'Ghost',"dex_number": 1013},
    {"name": 'Okidogi', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Poison',"type_2": 'Fighting',"dex_number": 1014},
    {"name": 'Munkidori', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Poison',"type_2": 'Psychic',"dex_number": 1015},
    {"name": 'Fezandipiti', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Poison',"type_2": 'Fairy',"dex_number": 1016},
    {"name": 'Ogerpon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 5,"type":'Grass',"type_2": 'Grass',"dex_number": 1017},
    {"name": 'Archaludon', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Steel',"type_2": 'Dragon',"dex_number": 1018},
    {"name": 'Hydrapple', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Grass',"type_2": 'Dragon',"dex_number": 1019},
    {"name": 'Gouging Fire', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Fire',"type_2": 'Dragon',"dex_number": 1020},
    {"name": 'Raging Bolt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Electric',"type_2": 'Dragon',"dex_number": 1021},
    {"name": 'Iron Boulder', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Rock',"type_2": 'Psychic',"dex_number": 1022},
    {"name": 'Iron Crown', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 10,"type":'Steel',"type_2": 'Psychic',"dex_number": 1023},
    {"name": 'Terapagos', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 255,"type":'Normal',"dex_number": 1024},
    {"name": 'Pecharunt', "caught": False,"amount caught": 0,"shiny caught": 0,"catch rate": 3,"type":'Poison',"type_2": 'Ghost',"dex_number": 1025},
]
# %% player data
player = {
    "party": [
        {"name": "Starter Carbink", "battles_won": 0, "Type": "Rock", "Type_2": "Fairy", "your_catch_rate": 200},
    ],
    "box": [ ## Pokemon in storage, waiting to be put in your party if you so choose

    ],
    "pokeballs": 10,
    "₽money": 1000,
}
# %% encounter and catch rates
weights_var = [
    pokedex[0]["catch rate"],
    pokedex[1]["catch rate"],
    pokedex[2]["catch rate"],
    pokedex[3]["catch rate"],
    pokedex[4]["catch rate"],
    pokedex[5]["catch rate"],
    pokedex[6]["catch rate"],
    pokedex[7]["catch rate"],
    pokedex[8]["catch rate"],
    pokedex[9]["catch rate"],
    pokedex[10]["catch rate"],
    pokedex[11]["catch rate"],
    pokedex[12]["catch rate"],
    pokedex[13]["catch rate"],
    pokedex[14]["catch rate"],
    pokedex[15]["catch rate"],
    pokedex[16]["catch rate"],
    pokedex[17]["catch rate"],
    pokedex[18]["catch rate"],
    pokedex[19]["catch rate"],
    pokedex[20]["catch rate"],
    pokedex[21]["catch rate"],
    pokedex[22]["catch rate"],
    pokedex[23]["catch rate"],
    pokedex[24]["catch rate"],
    pokedex[25]["catch rate"],
    pokedex[26]["catch rate"],
    pokedex[27]["catch rate"],
    pokedex[28]["catch rate"],
    pokedex[29]["catch rate"],
    pokedex[30]["catch rate"],
    pokedex[31]["catch rate"],
    pokedex[32]["catch rate"],
    pokedex[33]["catch rate"],
    pokedex[34]["catch rate"],
    pokedex[35]["catch rate"],
    pokedex[36]["catch rate"],
    pokedex[37]["catch rate"],
    pokedex[38]["catch rate"],
    pokedex[39]["catch rate"],
    pokedex[40]["catch rate"],
    pokedex[41]["catch rate"],
    pokedex[42]["catch rate"],
    pokedex[43]["catch rate"],
    pokedex[44]["catch rate"],
    pokedex[45]["catch rate"],
    pokedex[46]["catch rate"],
    pokedex[47]["catch rate"],
    pokedex[48]["catch rate"],
    pokedex[49]["catch rate"],
    pokedex[50]["catch rate"],
    pokedex[51]["catch rate"],
    pokedex[52]["catch rate"],
    pokedex[53]["catch rate"],
    pokedex[54]["catch rate"],
    pokedex[55]["catch rate"],
    pokedex[56]["catch rate"],
    pokedex[57]["catch rate"],
    pokedex[58]["catch rate"],
    pokedex[59]["catch rate"],
    pokedex[60]["catch rate"],
    pokedex[61]["catch rate"],
    pokedex[62]["catch rate"],
    pokedex[63]["catch rate"],
    pokedex[64]["catch rate"],
    pokedex[65]["catch rate"],
    pokedex[66]["catch rate"],
    pokedex[67]["catch rate"],
    pokedex[68]["catch rate"],
    pokedex[69]["catch rate"],
    pokedex[70]["catch rate"],
    pokedex[71]["catch rate"],
    pokedex[72]["catch rate"],
    pokedex[73]["catch rate"],
    pokedex[74]["catch rate"],
    pokedex[75]["catch rate"],
    pokedex[76]["catch rate"],
    pokedex[77]["catch rate"],
    pokedex[78]["catch rate"],
    pokedex[79]["catch rate"],
    pokedex[80]["catch rate"],
    pokedex[81]["catch rate"],
    pokedex[82]["catch rate"],
    pokedex[83]["catch rate"],
    pokedex[84]["catch rate"],
    pokedex[85]["catch rate"],
    pokedex[86]["catch rate"],
    pokedex[87]["catch rate"],
    pokedex[88]["catch rate"],
    pokedex[89]["catch rate"],
    pokedex[90]["catch rate"],
    pokedex[91]["catch rate"],
    pokedex[92]["catch rate"],
    pokedex[93]["catch rate"],
    pokedex[94]["catch rate"],
    pokedex[95]["catch rate"],
    pokedex[96]["catch rate"],
    pokedex[97]["catch rate"],
    pokedex[98]["catch rate"],
    pokedex[99]["catch rate"],
    pokedex[100]["catch rate"],
    pokedex[101]["catch rate"],
    pokedex[102]["catch rate"],
    pokedex[103]["catch rate"],
    pokedex[104]["catch rate"],
    pokedex[105]["catch rate"],
    pokedex[106]["catch rate"],
    pokedex[107]["catch rate"],
    pokedex[108]["catch rate"],
    pokedex[109]["catch rate"],
    pokedex[110]["catch rate"],
    pokedex[111]["catch rate"],
    pokedex[112]["catch rate"],
    pokedex[113]["catch rate"],
    pokedex[114]["catch rate"],
    pokedex[115]["catch rate"],
    pokedex[116]["catch rate"],
    pokedex[117]["catch rate"],
    pokedex[118]["catch rate"],
    pokedex[119]["catch rate"],
    pokedex[120]["catch rate"],
    pokedex[121]["catch rate"],
    pokedex[122]["catch rate"],
    pokedex[123]["catch rate"],
    pokedex[124]["catch rate"],
    pokedex[125]["catch rate"],
    pokedex[126]["catch rate"],
    pokedex[127]["catch rate"],
    pokedex[128]["catch rate"],
    pokedex[129]["catch rate"],
    pokedex[130]["catch rate"],
    pokedex[131]["catch rate"],
    pokedex[132]["catch rate"],
    pokedex[133]["catch rate"],
    pokedex[134]["catch rate"],
    pokedex[135]["catch rate"],
    pokedex[136]["catch rate"],
    pokedex[137]["catch rate"],
    pokedex[138]["catch rate"],
    pokedex[139]["catch rate"],
    pokedex[140]["catch rate"],
    pokedex[141]["catch rate"],
    pokedex[142]["catch rate"],
    pokedex[143]["catch rate"],
    pokedex[144]["catch rate"],
    pokedex[145]["catch rate"],
    pokedex[146]["catch rate"],
    pokedex[147]["catch rate"],
    pokedex[148]["catch rate"],
    pokedex[149]["catch rate"],
    pokedex[150]["catch rate"],
    pokedex[151]["catch rate"],
    pokedex[152]["catch rate"],
    pokedex[153]["catch rate"],
    pokedex[154]["catch rate"],
    pokedex[155]["catch rate"],
    pokedex[156]["catch rate"],
    pokedex[157]["catch rate"],
    pokedex[158]["catch rate"],
    pokedex[159]["catch rate"],
    pokedex[160]["catch rate"],
    pokedex[161]["catch rate"],
    pokedex[162]["catch rate"],
    pokedex[163]["catch rate"],
    pokedex[164]["catch rate"],
    pokedex[165]["catch rate"],
    pokedex[166]["catch rate"],
    pokedex[167]["catch rate"],
    pokedex[168]["catch rate"],
    pokedex[169]["catch rate"],
    pokedex[170]["catch rate"],
    pokedex[171]["catch rate"],
    pokedex[172]["catch rate"],
    pokedex[173]["catch rate"],
    pokedex[174]["catch rate"],
    pokedex[175]["catch rate"],
    pokedex[176]["catch rate"],
    pokedex[177]["catch rate"],
    pokedex[178]["catch rate"],
    pokedex[179]["catch rate"],
    pokedex[180]["catch rate"],
    pokedex[181]["catch rate"],
    pokedex[182]["catch rate"],
    pokedex[183]["catch rate"],
    pokedex[184]["catch rate"],
    pokedex[185]["catch rate"],
    pokedex[186]["catch rate"],
    pokedex[187]["catch rate"],
    pokedex[188]["catch rate"],
    pokedex[189]["catch rate"],
    pokedex[190]["catch rate"],
    pokedex[191]["catch rate"],
    pokedex[192]["catch rate"],
    pokedex[193]["catch rate"],
    pokedex[194]["catch rate"],
    pokedex[195]["catch rate"],
    pokedex[196]["catch rate"],
    pokedex[197]["catch rate"],
    pokedex[198]["catch rate"],
    pokedex[199]["catch rate"],
    pokedex[200]["catch rate"],
    pokedex[201]["catch rate"],
    pokedex[202]["catch rate"],
    pokedex[203]["catch rate"],
    pokedex[204]["catch rate"],
    pokedex[205]["catch rate"],
    pokedex[206]["catch rate"],
    pokedex[207]["catch rate"],
    pokedex[208]["catch rate"],
    pokedex[209]["catch rate"],
    pokedex[210]["catch rate"],
    pokedex[211]["catch rate"],
    pokedex[212]["catch rate"],
    pokedex[213]["catch rate"],
    pokedex[214]["catch rate"],
    pokedex[215]["catch rate"],
    pokedex[216]["catch rate"],
    pokedex[217]["catch rate"],
    pokedex[218]["catch rate"],
    pokedex[219]["catch rate"],
    pokedex[220]["catch rate"],
    pokedex[221]["catch rate"],
    pokedex[222]["catch rate"],
    pokedex[223]["catch rate"],
    pokedex[224]["catch rate"],
    pokedex[225]["catch rate"],
    pokedex[226]["catch rate"],
    pokedex[227]["catch rate"],
    pokedex[228]["catch rate"],
    pokedex[229]["catch rate"],
    pokedex[230]["catch rate"],
    pokedex[231]["catch rate"],
    pokedex[232]["catch rate"],
    pokedex[233]["catch rate"],
    pokedex[234]["catch rate"],
    pokedex[235]["catch rate"],
    pokedex[236]["catch rate"],
    pokedex[237]["catch rate"],
    pokedex[238]["catch rate"],
    pokedex[239]["catch rate"],
    pokedex[240]["catch rate"],
    pokedex[241]["catch rate"],
    pokedex[242]["catch rate"],
    pokedex[243]["catch rate"],
    pokedex[244]["catch rate"],
    pokedex[245]["catch rate"],
    pokedex[246]["catch rate"],
    pokedex[247]["catch rate"],
    pokedex[248]["catch rate"],
    pokedex[249]["catch rate"],
    pokedex[250]["catch rate"],
    pokedex[251]["catch rate"],
    pokedex[252]["catch rate"],
    pokedex[253]["catch rate"],
    pokedex[254]["catch rate"],
    pokedex[255]["catch rate"],
    pokedex[256]["catch rate"],
    pokedex[257]["catch rate"],
    pokedex[258]["catch rate"],
    pokedex[259]["catch rate"],
    pokedex[260]["catch rate"],
    pokedex[261]["catch rate"],
    pokedex[262]["catch rate"],
    pokedex[263]["catch rate"],
    pokedex[264]["catch rate"],
    pokedex[265]["catch rate"],
    pokedex[266]["catch rate"],
    pokedex[267]["catch rate"],
    pokedex[268]["catch rate"],
    pokedex[269]["catch rate"],
    pokedex[270]["catch rate"],
    pokedex[271]["catch rate"],
    pokedex[272]["catch rate"],
    pokedex[273]["catch rate"],
    pokedex[274]["catch rate"],
    pokedex[275]["catch rate"],
    pokedex[276]["catch rate"],
    pokedex[277]["catch rate"],
    pokedex[278]["catch rate"],
    pokedex[279]["catch rate"],
    pokedex[280]["catch rate"],
    pokedex[281]["catch rate"],
    pokedex[282]["catch rate"],
    pokedex[283]["catch rate"],
    pokedex[284]["catch rate"],
    pokedex[285]["catch rate"],
    pokedex[286]["catch rate"],
    pokedex[287]["catch rate"],
    pokedex[288]["catch rate"],
    pokedex[289]["catch rate"],
    pokedex[290]["catch rate"],
    pokedex[291]["catch rate"],
    pokedex[292]["catch rate"],
    pokedex[293]["catch rate"],
    pokedex[294]["catch rate"],
    pokedex[295]["catch rate"],
    pokedex[296]["catch rate"],
    pokedex[297]["catch rate"],
    pokedex[298]["catch rate"],
    pokedex[299]["catch rate"],
    pokedex[300]["catch rate"],
    pokedex[301]["catch rate"],
    pokedex[302]["catch rate"],
    pokedex[303]["catch rate"],
    pokedex[304]["catch rate"],
    pokedex[305]["catch rate"],
    pokedex[306]["catch rate"],
    pokedex[307]["catch rate"],
    pokedex[308]["catch rate"],
    pokedex[309]["catch rate"],
    pokedex[310]["catch rate"],
    pokedex[311]["catch rate"],
    pokedex[312]["catch rate"],
    pokedex[313]["catch rate"],
    pokedex[314]["catch rate"],
    pokedex[315]["catch rate"],
    pokedex[316]["catch rate"],
    pokedex[317]["catch rate"],
    pokedex[318]["catch rate"],
    pokedex[319]["catch rate"],
    pokedex[320]["catch rate"],
    pokedex[321]["catch rate"],
    pokedex[322]["catch rate"],
    pokedex[323]["catch rate"],
    pokedex[324]["catch rate"],
    pokedex[325]["catch rate"],
    pokedex[326]["catch rate"],
    pokedex[327]["catch rate"],
    pokedex[328]["catch rate"],
    pokedex[329]["catch rate"],
    pokedex[330]["catch rate"],
    pokedex[331]["catch rate"],
    pokedex[332]["catch rate"],
    pokedex[333]["catch rate"],
    pokedex[334]["catch rate"],
    pokedex[335]["catch rate"],
    pokedex[336]["catch rate"],
    pokedex[337]["catch rate"],
    pokedex[338]["catch rate"],
    pokedex[339]["catch rate"],
    pokedex[340]["catch rate"],
    pokedex[341]["catch rate"],
    pokedex[342]["catch rate"],
    pokedex[343]["catch rate"],
    pokedex[344]["catch rate"],
    pokedex[345]["catch rate"],
    pokedex[346]["catch rate"],
    pokedex[347]["catch rate"],
    pokedex[348]["catch rate"],
    pokedex[349]["catch rate"],
    pokedex[350]["catch rate"],
    pokedex[351]["catch rate"],
    pokedex[352]["catch rate"],
    pokedex[353]["catch rate"],
    pokedex[354]["catch rate"],
    pokedex[355]["catch rate"],
    pokedex[356]["catch rate"],
    pokedex[357]["catch rate"],
    pokedex[358]["catch rate"],
    pokedex[359]["catch rate"],
    pokedex[360]["catch rate"],
    pokedex[361]["catch rate"],
    pokedex[362]["catch rate"],
    pokedex[363]["catch rate"],
    pokedex[364]["catch rate"],
    pokedex[365]["catch rate"],
    pokedex[366]["catch rate"],
    pokedex[367]["catch rate"],
    pokedex[368]["catch rate"],
    pokedex[369]["catch rate"],
    pokedex[370]["catch rate"],
    pokedex[371]["catch rate"],
    pokedex[372]["catch rate"],
    pokedex[373]["catch rate"],
    pokedex[374]["catch rate"],
    pokedex[375]["catch rate"],
    pokedex[376]["catch rate"],
    pokedex[377]["catch rate"],
    pokedex[378]["catch rate"],
    pokedex[379]["catch rate"],
    pokedex[380]["catch rate"],
    pokedex[381]["catch rate"],
    pokedex[382]["catch rate"],
    pokedex[383]["catch rate"],
    pokedex[384]["catch rate"],
    pokedex[385]["catch rate"],
    pokedex[386]["catch rate"],
    pokedex[387]["catch rate"],
    pokedex[388]["catch rate"],
    pokedex[389]["catch rate"],
    pokedex[390]["catch rate"],
    pokedex[391]["catch rate"],
    pokedex[392]["catch rate"],
    pokedex[393]["catch rate"],
    pokedex[394]["catch rate"],
    pokedex[395]["catch rate"],
    pokedex[396]["catch rate"],
    pokedex[397]["catch rate"],
    pokedex[398]["catch rate"],
    pokedex[399]["catch rate"],
    pokedex[400]["catch rate"],
    pokedex[401]["catch rate"],
    pokedex[402]["catch rate"],
    pokedex[403]["catch rate"],
    pokedex[404]["catch rate"],
    pokedex[405]["catch rate"],
    pokedex[406]["catch rate"],
    pokedex[407]["catch rate"],
    pokedex[408]["catch rate"],
    pokedex[409]["catch rate"],
    pokedex[410]["catch rate"],
    pokedex[411]["catch rate"],
    pokedex[412]["catch rate"],
    pokedex[413]["catch rate"],
    pokedex[414]["catch rate"],
    pokedex[415]["catch rate"],
    pokedex[416]["catch rate"],
    pokedex[417]["catch rate"],
    pokedex[418]["catch rate"],
    pokedex[419]["catch rate"],
    pokedex[420]["catch rate"],
    pokedex[421]["catch rate"],
    pokedex[422]["catch rate"],
    pokedex[423]["catch rate"],
    pokedex[424]["catch rate"],
    pokedex[425]["catch rate"],
    pokedex[426]["catch rate"],
    pokedex[427]["catch rate"],
    pokedex[428]["catch rate"],
    pokedex[429]["catch rate"],
    pokedex[430]["catch rate"],
    pokedex[431]["catch rate"],
    pokedex[432]["catch rate"],
    pokedex[433]["catch rate"],
    pokedex[434]["catch rate"],
    pokedex[435]["catch rate"],
    pokedex[436]["catch rate"],
    pokedex[437]["catch rate"],
    pokedex[438]["catch rate"],
    pokedex[439]["catch rate"],
    pokedex[440]["catch rate"],
    pokedex[441]["catch rate"],
    pokedex[442]["catch rate"],
    pokedex[443]["catch rate"],
    pokedex[444]["catch rate"],
    pokedex[445]["catch rate"],
    pokedex[446]["catch rate"],
    pokedex[447]["catch rate"],
    pokedex[448]["catch rate"],
    pokedex[449]["catch rate"],
    pokedex[450]["catch rate"],
    pokedex[451]["catch rate"],
    pokedex[452]["catch rate"],
    pokedex[453]["catch rate"],
    pokedex[454]["catch rate"],
    pokedex[455]["catch rate"],
    pokedex[456]["catch rate"],
    pokedex[457]["catch rate"],
    pokedex[458]["catch rate"],
    pokedex[459]["catch rate"],
    pokedex[460]["catch rate"],
    pokedex[461]["catch rate"],
    pokedex[462]["catch rate"],
    pokedex[463]["catch rate"],
    pokedex[464]["catch rate"],
    pokedex[465]["catch rate"],
    pokedex[466]["catch rate"],
    pokedex[467]["catch rate"],
    pokedex[468]["catch rate"],
    pokedex[469]["catch rate"],
    pokedex[470]["catch rate"],
    pokedex[471]["catch rate"],
    pokedex[472]["catch rate"],
    pokedex[473]["catch rate"],
    pokedex[474]["catch rate"],
    pokedex[475]["catch rate"],
    pokedex[476]["catch rate"],
    pokedex[477]["catch rate"],
    pokedex[478]["catch rate"],
    pokedex[479]["catch rate"],
    pokedex[480]["catch rate"],
    pokedex[481]["catch rate"],
    pokedex[482]["catch rate"],
    pokedex[483]["catch rate"],
    pokedex[484]["catch rate"],
    pokedex[485]["catch rate"],
    pokedex[486]["catch rate"],
    pokedex[487]["catch rate"],
    pokedex[488]["catch rate"],
    pokedex[489]["catch rate"],
    pokedex[490]["catch rate"],
    pokedex[491]["catch rate"],
    pokedex[492]["catch rate"],
    pokedex[493]["catch rate"],
    pokedex[494]["catch rate"],
    pokedex[495]["catch rate"],
    pokedex[496]["catch rate"],
    pokedex[497]["catch rate"],
    pokedex[498]["catch rate"],
    pokedex[499]["catch rate"],
    pokedex[500]["catch rate"],
    pokedex[501]["catch rate"],
    pokedex[502]["catch rate"],
    pokedex[503]["catch rate"],
    pokedex[504]["catch rate"],
    pokedex[505]["catch rate"],
    pokedex[506]["catch rate"],
    pokedex[507]["catch rate"],
    pokedex[508]["catch rate"],
    pokedex[509]["catch rate"],
    pokedex[510]["catch rate"],
    pokedex[511]["catch rate"],
    pokedex[512]["catch rate"],
    pokedex[513]["catch rate"],
    pokedex[514]["catch rate"],
    pokedex[515]["catch rate"],
    pokedex[516]["catch rate"],
    pokedex[517]["catch rate"],
    pokedex[518]["catch rate"],
    pokedex[519]["catch rate"],
    pokedex[520]["catch rate"],
    pokedex[521]["catch rate"],
    pokedex[522]["catch rate"],
    pokedex[523]["catch rate"],
    pokedex[524]["catch rate"],
    pokedex[525]["catch rate"],
    pokedex[526]["catch rate"],
    pokedex[527]["catch rate"],
    pokedex[528]["catch rate"],
    pokedex[529]["catch rate"],
    pokedex[530]["catch rate"],
    pokedex[531]["catch rate"],
    pokedex[532]["catch rate"],
    pokedex[533]["catch rate"],
    pokedex[534]["catch rate"],
    pokedex[535]["catch rate"],
    pokedex[536]["catch rate"],
    pokedex[537]["catch rate"],
    pokedex[538]["catch rate"],
    pokedex[539]["catch rate"],
    pokedex[540]["catch rate"],
    pokedex[541]["catch rate"],
    pokedex[542]["catch rate"],
    pokedex[543]["catch rate"],
    pokedex[544]["catch rate"],
    pokedex[545]["catch rate"],
    pokedex[546]["catch rate"],
    pokedex[547]["catch rate"],
    pokedex[548]["catch rate"],
    pokedex[549]["catch rate"],
    pokedex[550]["catch rate"],
    pokedex[551]["catch rate"],
    pokedex[552]["catch rate"],
    pokedex[553]["catch rate"],
    pokedex[554]["catch rate"],
    pokedex[555]["catch rate"],
    pokedex[556]["catch rate"],
    pokedex[557]["catch rate"],
    pokedex[558]["catch rate"],
    pokedex[559]["catch rate"],
    pokedex[560]["catch rate"],
    pokedex[561]["catch rate"],
    pokedex[562]["catch rate"],
    pokedex[563]["catch rate"],
    pokedex[564]["catch rate"],
    pokedex[565]["catch rate"],
    pokedex[566]["catch rate"],
    pokedex[567]["catch rate"],
    pokedex[568]["catch rate"],
    pokedex[569]["catch rate"],
    pokedex[570]["catch rate"],
    pokedex[571]["catch rate"],
    pokedex[572]["catch rate"],
    pokedex[573]["catch rate"],
    pokedex[574]["catch rate"],
    pokedex[575]["catch rate"],
    pokedex[576]["catch rate"],
    pokedex[577]["catch rate"],
    pokedex[578]["catch rate"],
    pokedex[579]["catch rate"],
    pokedex[580]["catch rate"],
    pokedex[581]["catch rate"],
    pokedex[582]["catch rate"],
    pokedex[583]["catch rate"],
    pokedex[584]["catch rate"],
    pokedex[585]["catch rate"],
    pokedex[586]["catch rate"],
    pokedex[587]["catch rate"],
    pokedex[588]["catch rate"],
    pokedex[589]["catch rate"],
    pokedex[590]["catch rate"],
    pokedex[591]["catch rate"],
    pokedex[592]["catch rate"],
    pokedex[593]["catch rate"],
    pokedex[594]["catch rate"],
    pokedex[595]["catch rate"],
    pokedex[596]["catch rate"],
    pokedex[597]["catch rate"],
    pokedex[598]["catch rate"],
    pokedex[599]["catch rate"],
    pokedex[600]["catch rate"],
    pokedex[601]["catch rate"],
    pokedex[602]["catch rate"],
    pokedex[603]["catch rate"],
    pokedex[604]["catch rate"],
    pokedex[605]["catch rate"],
    pokedex[606]["catch rate"],
    pokedex[607]["catch rate"],
    pokedex[608]["catch rate"],
    pokedex[609]["catch rate"],
    pokedex[610]["catch rate"],
    pokedex[611]["catch rate"],
    pokedex[612]["catch rate"],
    pokedex[613]["catch rate"],
    pokedex[614]["catch rate"],
    pokedex[615]["catch rate"],
    pokedex[616]["catch rate"],
    pokedex[617]["catch rate"],
    pokedex[618]["catch rate"],
    pokedex[619]["catch rate"],
    pokedex[620]["catch rate"],
    pokedex[621]["catch rate"],
    pokedex[622]["catch rate"],
    pokedex[623]["catch rate"],
    pokedex[624]["catch rate"],
    pokedex[625]["catch rate"],
    pokedex[626]["catch rate"],
    pokedex[627]["catch rate"],
    pokedex[628]["catch rate"],
    pokedex[629]["catch rate"],
    pokedex[630]["catch rate"],
    pokedex[631]["catch rate"],
    pokedex[632]["catch rate"],
    pokedex[633]["catch rate"],
    pokedex[634]["catch rate"],
    pokedex[635]["catch rate"],
    pokedex[636]["catch rate"],
    pokedex[637]["catch rate"],
    pokedex[638]["catch rate"],
    pokedex[639]["catch rate"],
    pokedex[640]["catch rate"],
    pokedex[641]["catch rate"],
    pokedex[642]["catch rate"],
    pokedex[643]["catch rate"],
    pokedex[644]["catch rate"],
    pokedex[645]["catch rate"],
    pokedex[646]["catch rate"],
    pokedex[647]["catch rate"],
    pokedex[648]["catch rate"],
    pokedex[649]["catch rate"],
    pokedex[650]["catch rate"],
    pokedex[651]["catch rate"],
    pokedex[652]["catch rate"],
    pokedex[653]["catch rate"],
    pokedex[654]["catch rate"],
    pokedex[655]["catch rate"],
    pokedex[656]["catch rate"],
    pokedex[657]["catch rate"],
    pokedex[658]["catch rate"],
    pokedex[659]["catch rate"],
    pokedex[660]["catch rate"],
    pokedex[661]["catch rate"],
    pokedex[662]["catch rate"],
    pokedex[663]["catch rate"],
    pokedex[664]["catch rate"],
    pokedex[665]["catch rate"],
    pokedex[666]["catch rate"],
    pokedex[667]["catch rate"],
    pokedex[668]["catch rate"],
    pokedex[669]["catch rate"],
    pokedex[670]["catch rate"],
    pokedex[671]["catch rate"],
    pokedex[672]["catch rate"],
    pokedex[673]["catch rate"],
    pokedex[674]["catch rate"],
    pokedex[675]["catch rate"],
    pokedex[676]["catch rate"],
    pokedex[677]["catch rate"],
    pokedex[678]["catch rate"],
    pokedex[679]["catch rate"],
    pokedex[680]["catch rate"],
    pokedex[681]["catch rate"],
    pokedex[682]["catch rate"],
    pokedex[683]["catch rate"],
    pokedex[684]["catch rate"],
    pokedex[685]["catch rate"],
    pokedex[686]["catch rate"],
    pokedex[687]["catch rate"],
    pokedex[688]["catch rate"],
    pokedex[689]["catch rate"],
    pokedex[690]["catch rate"],
    pokedex[691]["catch rate"],
    pokedex[692]["catch rate"],
    pokedex[693]["catch rate"],
    pokedex[694]["catch rate"],
    pokedex[695]["catch rate"],
    pokedex[696]["catch rate"],
    pokedex[697]["catch rate"],
    pokedex[698]["catch rate"],
    pokedex[699]["catch rate"],
    pokedex[700]["catch rate"],
    pokedex[701]["catch rate"],
    pokedex[702]["catch rate"],
    pokedex[703]["catch rate"],
    pokedex[704]["catch rate"],
    pokedex[705]["catch rate"],
    pokedex[706]["catch rate"],
    pokedex[707]["catch rate"],
    pokedex[708]["catch rate"],
    pokedex[709]["catch rate"],
    pokedex[710]["catch rate"],
    pokedex[711]["catch rate"],
    pokedex[712]["catch rate"],
    pokedex[713]["catch rate"],
    pokedex[714]["catch rate"],
    pokedex[715]["catch rate"],
    pokedex[716]["catch rate"],
    pokedex[717]["catch rate"],
    pokedex[718]["catch rate"],
    pokedex[719]["catch rate"],
    pokedex[720]["catch rate"],
    pokedex[721]["catch rate"],
    pokedex[722]["catch rate"],
    pokedex[723]["catch rate"],
    pokedex[724]["catch rate"],
    pokedex[725]["catch rate"],
    pokedex[726]["catch rate"],
    pokedex[727]["catch rate"],
    pokedex[728]["catch rate"],
    pokedex[729]["catch rate"],
    pokedex[730]["catch rate"],
    pokedex[731]["catch rate"],
    pokedex[732]["catch rate"],
    pokedex[733]["catch rate"],
    pokedex[734]["catch rate"],
    pokedex[735]["catch rate"],
    pokedex[736]["catch rate"],
    pokedex[737]["catch rate"],
    pokedex[738]["catch rate"],
    pokedex[739]["catch rate"],
    pokedex[740]["catch rate"],
    pokedex[741]["catch rate"],
    pokedex[742]["catch rate"],
    pokedex[743]["catch rate"],
    pokedex[744]["catch rate"],
    pokedex[745]["catch rate"],
    pokedex[746]["catch rate"],
    pokedex[747]["catch rate"],
    pokedex[748]["catch rate"],
    pokedex[749]["catch rate"],
    pokedex[750]["catch rate"],
    pokedex[751]["catch rate"],
    pokedex[752]["catch rate"],
    pokedex[753]["catch rate"],
    pokedex[754]["catch rate"],
    pokedex[755]["catch rate"],
    pokedex[756]["catch rate"],
    pokedex[757]["catch rate"],
    pokedex[758]["catch rate"],
    pokedex[759]["catch rate"],
    pokedex[760]["catch rate"],
    pokedex[761]["catch rate"],
    pokedex[762]["catch rate"],
    pokedex[763]["catch rate"],
    pokedex[764]["catch rate"],
    pokedex[765]["catch rate"],
    pokedex[766]["catch rate"],
    pokedex[767]["catch rate"],
    pokedex[768]["catch rate"],
    pokedex[769]["catch rate"],
    pokedex[770]["catch rate"],
    pokedex[771]["catch rate"],
    pokedex[772]["catch rate"],
    pokedex[773]["catch rate"],
    pokedex[774]["catch rate"],
    pokedex[775]["catch rate"],
    pokedex[776]["catch rate"],
    pokedex[777]["catch rate"],
    pokedex[778]["catch rate"],
    pokedex[779]["catch rate"],
    pokedex[780]["catch rate"],
    pokedex[781]["catch rate"],
    pokedex[782]["catch rate"],
    pokedex[783]["catch rate"],
    pokedex[784]["catch rate"],
    pokedex[785]["catch rate"],
    pokedex[786]["catch rate"],
    pokedex[787]["catch rate"],
    pokedex[788]["catch rate"],
    pokedex[789]["catch rate"],
    pokedex[790]["catch rate"],
    pokedex[791]["catch rate"],
    pokedex[792]["catch rate"],
    pokedex[793]["catch rate"],
    pokedex[794]["catch rate"],
    pokedex[795]["catch rate"],
    pokedex[796]["catch rate"],
    pokedex[797]["catch rate"],
    pokedex[798]["catch rate"],
    pokedex[799]["catch rate"],
    pokedex[800]["catch rate"],
    pokedex[801]["catch rate"],
    pokedex[802]["catch rate"],
    pokedex[803]["catch rate"],
    pokedex[804]["catch rate"],
    pokedex[805]["catch rate"],
    pokedex[806]["catch rate"],
    pokedex[807]["catch rate"],
    pokedex[808]["catch rate"],
    pokedex[809]["catch rate"],
    pokedex[810]["catch rate"],
    pokedex[811]["catch rate"],
    pokedex[812]["catch rate"],
    pokedex[813]["catch rate"],
    pokedex[814]["catch rate"],
    pokedex[815]["catch rate"],
    pokedex[816]["catch rate"],
    pokedex[817]["catch rate"],
    pokedex[818]["catch rate"],
    pokedex[819]["catch rate"],
    pokedex[820]["catch rate"],
    pokedex[821]["catch rate"],
    pokedex[822]["catch rate"],
    pokedex[823]["catch rate"],
    pokedex[824]["catch rate"],
    pokedex[825]["catch rate"],
    pokedex[826]["catch rate"],
    pokedex[827]["catch rate"],
    pokedex[828]["catch rate"],
    pokedex[829]["catch rate"],
    pokedex[830]["catch rate"],
    pokedex[831]["catch rate"],
    pokedex[832]["catch rate"],
    pokedex[833]["catch rate"],
    pokedex[834]["catch rate"],
    pokedex[835]["catch rate"],
    pokedex[836]["catch rate"],
    pokedex[837]["catch rate"],
    pokedex[838]["catch rate"],
    pokedex[839]["catch rate"],
    pokedex[840]["catch rate"],
    pokedex[841]["catch rate"],
    pokedex[842]["catch rate"],
    pokedex[843]["catch rate"],
    pokedex[844]["catch rate"],
    pokedex[845]["catch rate"],
    pokedex[846]["catch rate"],
    pokedex[847]["catch rate"],
    pokedex[848]["catch rate"],
    pokedex[849]["catch rate"],
    pokedex[850]["catch rate"],
    pokedex[851]["catch rate"],
    pokedex[852]["catch rate"],
    pokedex[853]["catch rate"],
    pokedex[854]["catch rate"],
    pokedex[855]["catch rate"],
    pokedex[856]["catch rate"],
    pokedex[857]["catch rate"],
    pokedex[858]["catch rate"],
    pokedex[859]["catch rate"],
    pokedex[860]["catch rate"],
    pokedex[861]["catch rate"],
    pokedex[862]["catch rate"],
    pokedex[863]["catch rate"],
    pokedex[864]["catch rate"],
    pokedex[865]["catch rate"],
    pokedex[866]["catch rate"],
    pokedex[867]["catch rate"],
    pokedex[868]["catch rate"],
    pokedex[869]["catch rate"],
    pokedex[870]["catch rate"],
    pokedex[871]["catch rate"],
    pokedex[872]["catch rate"],
    pokedex[873]["catch rate"],
    pokedex[874]["catch rate"],
    pokedex[875]["catch rate"],
    pokedex[876]["catch rate"],
    pokedex[877]["catch rate"],
    pokedex[878]["catch rate"],
    pokedex[879]["catch rate"],
    pokedex[880]["catch rate"],
    pokedex[881]["catch rate"],
    pokedex[882]["catch rate"],
    pokedex[883]["catch rate"],
    pokedex[884]["catch rate"],
    pokedex[885]["catch rate"],
    pokedex[886]["catch rate"],
    pokedex[887]["catch rate"],
    pokedex[888]["catch rate"],
    pokedex[889]["catch rate"],
    pokedex[890]["catch rate"],
    pokedex[891]["catch rate"],
    pokedex[892]["catch rate"],
    pokedex[893]["catch rate"],
    pokedex[894]["catch rate"],
    pokedex[895]["catch rate"],
    pokedex[896]["catch rate"],
    pokedex[897]["catch rate"],
    pokedex[898]["catch rate"],
    pokedex[899]["catch rate"],
    pokedex[900]["catch rate"],
    pokedex[901]["catch rate"],
    pokedex[902]["catch rate"],
    pokedex[903]["catch rate"],
    pokedex[904]["catch rate"],
    pokedex[905]["catch rate"],
    pokedex[906]["catch rate"],
    pokedex[907]["catch rate"],
    pokedex[908]["catch rate"],
    pokedex[909]["catch rate"],
    pokedex[910]["catch rate"],
    pokedex[911]["catch rate"],
    pokedex[912]["catch rate"],
    pokedex[913]["catch rate"],
    pokedex[914]["catch rate"],
    pokedex[915]["catch rate"],
    pokedex[916]["catch rate"],
    pokedex[917]["catch rate"],
    pokedex[918]["catch rate"],
    pokedex[919]["catch rate"],
    pokedex[920]["catch rate"],
    pokedex[921]["catch rate"],
    pokedex[922]["catch rate"],
    pokedex[923]["catch rate"],
    pokedex[924]["catch rate"],
    pokedex[925]["catch rate"],
    pokedex[926]["catch rate"],
    pokedex[927]["catch rate"],
    pokedex[928]["catch rate"],
    pokedex[929]["catch rate"],
    pokedex[930]["catch rate"],
    pokedex[931]["catch rate"],
    pokedex[932]["catch rate"],
    pokedex[933]["catch rate"],
    pokedex[934]["catch rate"],
    pokedex[935]["catch rate"],
    pokedex[936]["catch rate"],
    pokedex[937]["catch rate"],
    pokedex[938]["catch rate"],
    pokedex[939]["catch rate"],
    pokedex[940]["catch rate"],
    pokedex[941]["catch rate"],
    pokedex[942]["catch rate"],
    pokedex[943]["catch rate"],
    pokedex[944]["catch rate"],
    pokedex[945]["catch rate"],
    pokedex[946]["catch rate"],
    pokedex[947]["catch rate"],
    pokedex[948]["catch rate"],
    pokedex[949]["catch rate"],
    pokedex[950]["catch rate"],
    pokedex[951]["catch rate"],
    pokedex[952]["catch rate"],
    pokedex[953]["catch rate"],
    pokedex[954]["catch rate"],
    pokedex[955]["catch rate"],
    pokedex[956]["catch rate"],
    pokedex[957]["catch rate"],
    pokedex[958]["catch rate"],
    pokedex[959]["catch rate"],
    pokedex[960]["catch rate"],
    pokedex[961]["catch rate"],
    pokedex[962]["catch rate"],
    pokedex[963]["catch rate"],
    pokedex[964]["catch rate"],
    pokedex[965]["catch rate"],
    pokedex[966]["catch rate"],
    pokedex[967]["catch rate"],
    pokedex[968]["catch rate"],
    pokedex[969]["catch rate"],
    pokedex[970]["catch rate"],
    pokedex[971]["catch rate"],
    pokedex[972]["catch rate"],
    pokedex[973]["catch rate"],
    pokedex[974]["catch rate"],
    pokedex[975]["catch rate"],
    pokedex[976]["catch rate"],
    pokedex[977]["catch rate"],
    pokedex[978]["catch rate"],
    pokedex[979]["catch rate"],
    pokedex[980]["catch rate"],
    pokedex[981]["catch rate"],
    pokedex[982]["catch rate"],
    pokedex[983]["catch rate"],
    pokedex[984]["catch rate"],
    pokedex[985]["catch rate"],
    pokedex[986]["catch rate"],
    pokedex[987]["catch rate"],
    pokedex[988]["catch rate"],
    pokedex[989]["catch rate"],
    pokedex[990]["catch rate"],
    pokedex[991]["catch rate"],
    pokedex[992]["catch rate"],
    pokedex[993]["catch rate"],
    pokedex[994]["catch rate"],
    pokedex[995]["catch rate"],
    pokedex[996]["catch rate"],
    pokedex[997]["catch rate"],
    pokedex[998]["catch rate"],
    pokedex[999]["catch rate"],
    pokedex[1000]["catch rate"],
    pokedex[1001]["catch rate"],
    pokedex[1002]["catch rate"],
    pokedex[1003]["catch rate"],
    pokedex[1004]["catch rate"],
    pokedex[1005]["catch rate"],
    pokedex[1006]["catch rate"],
    pokedex[1007]["catch rate"],
    pokedex[1008]["catch rate"],
    pokedex[1009]["catch rate"],
    pokedex[1010]["catch rate"],
    pokedex[1011]["catch rate"],
    pokedex[1012]["catch rate"],
    pokedex[1013]["catch rate"],
    pokedex[1014]["catch rate"],
    pokedex[1015]["catch rate"],
    pokedex[1016]["catch rate"],
    pokedex[1017]["catch rate"],
    pokedex[1018]["catch rate"],
    pokedex[1019]["catch rate"],
    pokedex[1020]["catch rate"],
    pokedex[1021]["catch rate"],
    pokedex[1022]["catch rate"],
    pokedex[1023]["catch rate"],
    pokedex[1024]["catch rate"],
]
# %% shop
def shop(variables, player):
    in_shop = True ## makes the shop loop
    print("You found a shop! Do you want to buy anything? You can also check your pokedex")
    while in_shop == True and variables["purchases"] <= 6: ## stops the shop after 6 purchases
        for x in player["party"]:
            print("Party:")
            print(x) ## prints your party
        print("Stock: (₽10)Pokeball, ")
        buy_options = input("What do you buy? (1 for the first option, 2 for the second, etc... (press L or l to leave the shop, or press p or P to check pokedex, you may only but up to 7 items)) ")
        if buy_options == "1" and variables["purchases"] >= 6:
            print("You have maxed your credit card! please wait until the next battle is finished")
            shop(variables, player)
        elif buy_options == "1" and player["₽money"] >= 10: ## buys a Pokeball
            player["₽money"] -= 10
            player["pokeballs"] += 1
            variables["purchases"] += 1
            print("pokeballs:", player["pokeballs"])
        elif buy_options == "p" or buy_options == "P":
            print("Pokedex:")
            for x in pokedex[0:1025]: ## prints your pokedex
                if x["caught"] == True:
                    print(x)
        elif buy_options == "1" and player["₽money"] < 10:
            print("You dont have enough money!")
            shop(variables, player)
        elif buy_options == "l" or buy_options == "L": ## leaves the shop
            in_shop = False
            print("On to adventure!")
            adventure(variables, player)
        else:
            print("Please type one of the options")
            shop(variables, player)
# %% box swapping
def box(variables, player):
    print("Box:")
    for x in player["box"]:
        print(x)
    box_swap = input("Which pokemon do you want to take out of your box(type the number, starting at 1), type L or l to leave: ")
    if box_swap == "1" or box_swap == "2" or box_swap == "3" or box_swap == "4" or box_swap == "5" or box_swap == "6":
        if len(player["party"]) >= 6:
            party_change = input("Party full! Choose a pokemon to take out: ")
            if party_change == "1" or party_change == "2" or party_change == "3" or party_change == "4" or party_change == "5" or party_change == "6":
                moving_party = player["party"].pop(int(party_change) - 1)
                moving_pokemon = player["box"].pop(int(box_swap) - 1)
                player["party"].append(moving_pokemon)
                player["box"].append(moving_party)
                print("Party:")
                for x in player["party"]:
                    print(x)
                box(variables, player)
            else:
                print("Please type one of the options")
        else:
            moving_pokemon = player["box"].pop(int(box_swap) - 1)
            player["party"].append(moving_pokemon)
            print("Party:")
            for x in player["party"]:
                print(x)
            box(variables, player)
        print(f'Box: {player["box"]}')
        print(f'Party: {player["party"]}')
        adventure(variables, player)
    elif box_swap == "l" or box_swap == "L":
        adventure(variables, player)
    else:
        print("Please type one of the options")
        box(variables, player)
# %% encounter options
def encounter_root(variables, player):
    variables["first_turn"] = True ## changes diolouge on the first turn
    variables["purchases"] = 0
    print(f"You encountered {variables['encounter_name']}!")
    print(player["party"][0]["name"], "was sent out!")
    while variables["turn"] <= 5: ## limits encounter turns
        variables["turn"] += 1
        print("pokeballs:", player["pokeballs"])
        if variables["first_turn"] == True:
            variables["encounter_choices"] = input("What will you do? (1) Throw pokeball, (2) Change pokemon, (3) Battle, (4) Try to flee: ") ## choices mid encounter
        else:
            variables["encounter_choices"] = input(f"It's still {variables['encounter_name']}! What will you do? (1) Throw pokeball, (2) Change pokemon, (3) Battle, (4) Try to flee: ")
        variables["first_turn"] = False
        if variables["encounter_choices"] == "1" and player["pokeballs"] >= 1:
            catch_func(variables, player)
        elif variables["encounter_choices"] == "1" and player["pokeballs"] <= 0:
            _0_pokeballs(variables, player)
        elif variables["encounter_choices"] == "2":
            reorder_party(variables, player)
        elif variables["encounter_choices"] == "3":
            battle_func(variables, player)
        elif variables["encounter_choices"] == "4":
            flee(variables, player)
        else:
            print("Please type one of the options")
            encounter_root(variables, player)
    print("The pokemon fled, and you return to home base...")
    adventure(variables, player)
# %% option: battle
def battle_func(variables, player):
    super_effective = 0
    not_very_effective = 0
    no_effect = False
    if len(player["party"][0]) == 5 and variables["has_type_2"] == True:
        if (
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Normal" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Dark"
        ):
            super_effective += 1
        if (
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type_2"] == "Steel"
        ):
            super_effective -= 1
        if (
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type_2"] == "Normal" or 
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type_2"] == "Fairy"
        ):
            no_effect = True
    if len(player["party"][0]) >= 4 and variables["has_type_2"] == True:
        if (
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Normal" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Dark"
        ):
            super_effective += 1
        if (
            player["party"][0]["Type"] == "Normal" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Normal" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Grass" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Bug" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type_2"] == "Psycic" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Ice" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Rock" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type_2"] == "Fighting" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type_2"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type_2"] == "Fairy" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Water" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Electric" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Fire" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Poison" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type_2"] == "Steel"
        ):
            super_effective -= 1
        if (
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type_2"] == "Normal" or 
            player["party"][0]["Type"] == "Normal" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type_2"] == "Ghost" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type_2"] == "Ground" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type_2"] == "Flying" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type_2"] == "Dark" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type_2"] == "Steel" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type_2"] == "Fairy"
        ):
            no_effect = True 
    if len(player["party"][0]) == 5 and variables["has_type_2"] == False:
        if (
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Normal" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Dark"
        ):
            super_effective += 1
        if (
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Fire" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Water" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Grass" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Ice" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Flying" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Bug" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Rock" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type_2"] == "Dark" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type_2"] == "Steel" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type_2"] == "Fairy" and variables["encounter_type"] == "Steel"
        ):
            super_effective -= 1
        if (
            player["party"][0]["Type_2"] == "Ghost" and variables["encounter_type"] == "Normal" or 
            player["party"][0]["Type_2"] == "Normal" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Fighting" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type_2"] == "Electric" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type_2"] == "Ground" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type_2"] == "Psycic" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type_2"] == "Poison" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type_2"] == "Dragon" and variables["encounter_type"] == "Fairy"
        ):
            no_effect = True
    if len(player["party"][0]) >= 4 and variables["has_type_2"] == False:
        if (
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Normal" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Dark"
        ):
            super_effective += 1
        if (
            player["party"][0]["Type"] == "Normal" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Normal" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Fire" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Water" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Grass" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Ice" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Grass" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Bug" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Flying" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type"] == "Psycic" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Ice" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Rock" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Bug" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Rock" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type"] == "Fighting" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type"] == "Dragon" or 
            player["party"][0]["Type"] == "Dark" and variables["encounter_type"] == "Fairy" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Water" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Electric" or 
            player["party"][0]["Type"] == "Steel" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Fire" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Poison" or 
            player["party"][0]["Type"] == "Fairy" and variables["encounter_type"] == "Steel"
        ):
            super_effective -= 1
        if (
            player["party"][0]["Type"] == "Ghost" and variables["encounter_type"] == "Normal" or 
            player["party"][0]["Type"] == "Normal" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type"] == "Fighting" and variables["encounter_type"] == "Ghost" or 
            player["party"][0]["Type"] == "Electric" and variables["encounter_type"] == "Ground" or 
            player["party"][0]["Type"] == "Ground" and variables["encounter_type"] == "Flying" or 
            player["party"][0]["Type"] == "Psycic" and variables["encounter_type"] == "Dark" or 
            player["party"][0]["Type"] == "Poison" and variables["encounter_type"] == "Steel" or 
            player["party"][0]["Type"] == "Dragon" and variables["encounter_type"] == "Fairy"
        ):
            no_effect = True
    if no_effect == True:
        your_power = 0
    else:
        if super_effective >= 1:
            your_power = (300 - int(player["party"][0]["your_catch_rate"]))*(2^(super_effective))
        elif super_effective == 0:
            your_power = 300 - int(player["party"][0]["your_catch_rate"])
        else:
            your_power = (300 - int(player["party"][0]["your_catch_rate"]))/(2^(super_effective))
    their_power = 300 - int(variables["encounter_catch_rate"])
    print(your_power, their_power)
    if your_power > their_power:
        print("You won!")
        player["₽money"] += 10
        print("Your money: ")
        print(player["₽money"])
        player["party"][0]["battles_won"] += 1
        adventure(variables, player)
    else:
        print("You lost...")
        adventure(variables, player)
# %% option: catch
def catch_func(variables, player):
    player["pokeballs"] -= 1
    ## checks critical catch, shiny, and if you caught
    variables["crit_catch"] = random.randint(1, 100)
    variables["catch_chance"] = random.randint(1, (round(300/int(variables["encounter_catch_rate"])))) ## a randomizer based on catch rate
    variables["shiny_chance"] = random.randint(1, 1000)
    if variables["has_type_2"] == True:
        dict_type_2_shiny = {
            'name': f"{variables['encounter_name']}(shiny)", 'battles_won': 0, 'Type': variables['encounter_type'], 'Type_2': variables['encounter_type_2'], 'your_catch_rate': variables['encounter_catch_rate']
        }
    else:
        dict_shiny = {
            'name': f"{variables['encounter_name']}(shiny)", 'battles_won': 0, 'Type': variables['encounter_type'], 'your_catch_rate': variables['encounter_catch_rate']
        }
    if variables["has_type_2"] == True:
        dict_type_2 = {
            'name': variables['encounter_name'], 'battles_won': 0, 'Type': variables['encounter_type'], 'Type_2': variables['encounter_type_2'], 'your_catch_rate': variables['encounter_catch_rate']
        }
    else:
        dict_normal = {
            'name': variables['encounter_name'], 'battles_won': 0, 'Type': variables['encounter_type'], 'your_catch_rate': variables['encounter_catch_rate']
        }
    if variables["crit_catch"] == 100 and variables["shiny_chance"] == 1000:
        pokedex[variables['dex_number']]["shiny caught"] += 1
        pokedex[variables['dex_number']]["amount caught"] += 1
        pokedex[variables['dex_number']]["caught"] = True
        print("CRITICAL CATCH!!! (This pokemon looks a little different)(I'm honestly very impressed, get a life though, that was a 1/100,000 chance)")
        if f"{variables['encounter_name']}(shiny)" in pokedex:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2_shiny) ## adds the pokemon to your party
                else:
                    player["party"].append(dict_shiny) ## adds the pokemon to your party
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2_shiny) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_shiny) ## adds the pokemon to your box
        else:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2_shiny) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_shiny) ## adds the pokemon to your party/box
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2_shiny) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_shiny) ## adds the pokemon to your box
        adventure(variables, player)
    elif variables["catch_chance"] == round(300/int(variables["encounter_catch_rate"])) and variables["shiny_chance"] == 1000:
        pokedex[variables['dex_number']]["amount caught"] += 1
        pokedex[variables['dex_number']]["shiny caught"] += 1
        pokedex[variables['dex_number']]["caught"] = True
        print(f"{variables['encounter_name']} was caught! (This pokemon looks a little different)")
        if f"{variables['encounter_name']}(shiny)" in pokedex:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2_shiny) ## adds the pokemon to your party
                else:
                    player["party"].append(dict_shiny) ## adds the pokemon to your party
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2_shiny) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_shiny) ## adds the pokemon to your box
        else:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2_shiny) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_shiny) ## adds the pokemon to your party/box
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2_shiny) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_shiny) ## adds the pokemon to your box
        adventure(variables, player)
    elif variables["crit_catch"] == 100:
        pokedex[variables['dex_number']]["amount caught"] += 1
        pokedex[variables['dex_number']]["caught"] = True
        print("CRITICAL CATCH!!!")
        if f"{variables['encounter_name']}" in pokedex:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2) ## adds the pokemon to your party
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_normal) ## adds the pokemon to your box
        else:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2) ## adds the pokemon to your party
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2) ## adds the pokemon to your box
                else:
                    player["box"].append(dict_normal) ## adds the pokemon to your box
        adventure(variables, player)
    elif variables["catch_chance"] == round(300/int(variables["encounter_catch_rate"])):
        pokedex[variables['dex_number']]["amount caught"] += 1
        pokedex[variables['dex_number']]["caught"] = True
        print(f"{variables['encounter_name']} was caught!")
        if f"{variables['encounter_name']}" in pokedex:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party/box
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party/box
        else:
            if len(player["party"]) < 6:
                if variables["has_type_2"] == True:
                    player["party"].append(dict_type_2) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party/box
            else:
                if variables["has_type_2"] == True:
                    player["box"].append(dict_type_2) ## adds the pokemon to your party/box
                else:
                    player["party"].append(dict_normal) ## adds the pokemon to your party/box
        adventure(variables, player)
    else:
        print(f"Bwoop, Bwoop, Bang! {variables['encounter_name']} broke free!")
# %% no pokeballs
def _0_pokeballs(variables, player): ## sends you to the main menu if you have no pokeballs
    print("No pokeballs left!")
    adventure(variables, player)
# %% option: reorder party
def reorder_party(variables, player):
    for x in player["party"]:
        print(x)
    party_change = input("Type the number of the party member to send out, 1 for the first, 2 for the second, etc... up to 6, or L or l to leave: ")
    if party_change == "1" or party_change == "2" or party_change == "3" or party_change == "4" or party_change == "5" or party_change == "6":
        if len(player["party"]) < int(party_change):
            print("Choose a pokemon that exists")
            variables["turn"] -= 1
            reorder_party(variables, player)
        else: ## sends out the selected pokemon
            moving_var = player["party"].pop(int(party_change) - 1)
            print(moving_var)
            player["party"].insert(0, moving_var)
            for x in player["party"]:
                print(x)
    elif party_change == "L" or party_change == "l":
        variables["turn"] -= 1
        encounter_root(variables, player)
    else:
        print("Please type one of the options")
        variables["turn"] -= 1
        reorder_party(variables, player)
    encounter_root(variables, player)
# %% option: flee
def flee(variables, player):
    flee_success = random.randint(1, (round(300/int(variables["encounter_catch_rate"]))))
    if flee_success == round(300/int(variables["encounter_catch_rate"])):
        print("You fled the battle!")
        variables["turn"] = 0
        adventure(variables, player)
    else:
        print("You failed to flee...")
        encounter_root(variables, player)
# %% main menu
# Main menu
def adventure(variables, player):
    action = input("(1) Encounter, (2) Shop, (3) Box or (Q or q) Quit: ")
    variables["turn"] = 0
    variables["has_type_2"] = False
    if action == "1":
        variables["encounter"] = random.choices(population=list(pokedex), weights=weights_var, k=1)
        variables["encounter_name"] = variables["encounter"][0]["name"]
        variables["encounter_caught"] = variables["encounter"][0]["caught"]
        variables["encounter_amount_caught"] = variables["encounter"][0]["amount caught"]
        variables["encounter_shiny_caught"] = variables["encounter"][0]["shiny caught"]
        variables["encounter_catch_rate"] = variables["encounter"][0]["catch rate"]
        variables["encounter_type"] = variables["encounter"][0]["type"]
        if "type_2" in variables["encounter"][0]:
            variables["encounter_type_2"] = variables["encounter"][0]["type_2"]
            variables["has_type_2"] = True
        variables["dex_number"] = variables["encounter"][0]["dex_number"]
        encounter_root(variables, player)
    elif action == "2":
        shop(variables, player)
    elif action == "3":
        box(variables, player)
    elif action == "Q" or action == "q":
        print("You quit! Next time press the little trash can button")
    else:
        print("Please type one of the options")
        adventure(variables, player)
# %% Function calling
adventure(variables, player)
