# Features

1. This forces to template a `bash` script and helps to create a menu driven approach.
2. It favours `convention over configuration` which means any new member can onboard very quickly and needn't customise e.g. any paths.

# How to contribute
- Use `example_script.sh` as a template and ensure you leave the following:
  - `--help` 
  - `--version`
- Just run `script_menu` as-is to see the menu

*️⃣ alias menu.sh in mac profile to therefore run anywhere

---
# TODO
- [ ] speed up - _use `find` instead of `ls` to get all files_
```shell
# Store the description and usage in an associative array
declare -A DESCRIPTIONS USAGES

for ((i=0; i<${#SCRIPTS[@]}; i++)); do
    description=$(get_description ${SCRIPTS[$i]})
    usage=$(get_usage ${SCRIPTS[$i]})
    DESCRIPTIONS[${SCRIPTS[$i]}]="$description"
    USAGES[${SCRIPTS[$i]}]="$usage"
    length=${#description}
    if [[ $length -gt $max_length_desc ]]; then
        max_length_desc=$length
    fi
    if [[ ${#SCRIPTS[$i]} -gt $max_length_name ]]; then
        max_length_name=${#SCRIPTS[$i]}
    fi
done
```
- [ ] Add aws describe resource per type
- [ ] Add aws describe resource per tag 
- [ ] Add aws tag monitoring