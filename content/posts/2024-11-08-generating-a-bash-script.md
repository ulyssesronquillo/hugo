---
author: ulysses
title: 'generating a bash script'
date: 2024-11-08
slug: generating-a-bash-script
draft: false
---

Here's the code for a bash script that generates another bash script and then executes it, as well as deletes it in the end.

```
#!/bin/bash

# Define the script content
script_content='#!/bin/bash
echo "Hello, this is the generated script!"
echo "The current date and time is: $(date)"
'

# Define the name of the new script
new_script="generated_script.sh"

# Write the content to the new script file
echo "$script_content" > "$new_script"

# Make the new script executable
chmod +x "$new_script"

# Execute the new script
./"$new_script"

rm -f $new_script
```
