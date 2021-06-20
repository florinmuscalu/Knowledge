- YAML files use .yml extension.
- YAML is case-sensitive.
- Uses indents for structure.
- Uses spaces, not tabs.
- YAML documents start with three dashes ***---***
- Comments begin with a **#**
- Strings don't need quotes unless they include special characters
- Structures:
    - Mappings
	- Sequences

YAML is used mostly to store configuration data, such as in Ansible Playbooks and OpenStack Heat templates.

YAML Mappings are key-value pairs, similar to JSON objects.

Example:
```yaml
---
name : Bob
height : 6 foot
```
YAML Sequences are lists or arrays of data, similar to JSON arrays. Sequence items start with a dash **-**

Example:
```yaml
---
-apple
-orange
-banana
```
The sequences do not need to have a name associated with them.

Nested mappings and sequences:
```yaml
---
Fruit:
- apple
- orange
- banana
Vegetable:
    cruciferous:
    - radish
    - wasabi
    gourd:
    - cucumber
    - pumpkin
```
The **Fruit** mapping (object) has a nested sequence. The **Vegetable** mapping has nested mappings **cruciferous** and **gourd**. The cruciferous and gourd mappings have their own nested sequences. Whitespaces indicate nesting.
