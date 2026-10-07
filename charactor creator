# Define the visual representations for the character stat bar
full_dot = '●'
empty_dot = '○'

def create_character(name, strength, intelligence, charisma):
    # --- Name Validation ---
    # Ensure the name is of string type
    if not isinstance(name, str):
        return "The character name should be a string"
    # Ensure the name is not empty
    elif name == "":
        return "The character should have a name"
    # Restrict character name length to 10 characters max
    elif len(name) > 10:
        return "The character name is too long"
    # Prevent names from containing spaces
    elif " " in name:
        return "The character name should not contain spaces"
    else:
        pass

    # Group stats into a dictionary for validation and easier looping
    stats = {'STR': strength, 'INT': intelligence, 'CHA': charisma}
    
    # --- Stat Validations ---
    # 1. Ensure all stat values are integers
    for stat in stats.values():
        if not isinstance(stat, int):
            return "All stats should be integers"
    # 2. Ensure each stat value is at least 1
    for stat in stats.values():
        if stat < 1:
            return "All stats should be no less than 1"
    # 3. Ensure no single stat exceeds a maximum value of 4
    for stat in stats.values():
        if stat > 4:
            return "All stats should be no more than 4"
    # 4. Enforce that the starting stat points sum exactly to 7
    if sum(stats.values()) != 7:
        return "The character should start with 7 points"

    # --- Build Character Visual Sheet ---
    # Initialize the output string with the character's name
    char_string = name
    
    # Append each stat line-by-line using horizontal bar-chart style indicators
    for key in stats.keys():
        stat = stats[key]
        # Construct a 10-character bar consisting of filled and empty dots
        char_string += f'\n{key} {full_dot*stat}{empty_dot*(10-stat)}'

    return char_string

# Instantiate a test character with points allocated (1 + 4 + 2 = 7)
output = create_character('ren', 4, 2, 1)
print(output)
