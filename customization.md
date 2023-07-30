# Customization


## Directories
</br>
documented in `database/directories.ini`
</br></br>

## Language:
* Supported languages: english, french
* Default language is `french`
* To select another language:
    - (**preferred**) for english language: create an empty file named `en` in `database` directory
    - or set in `database/common.ini` file
    - or use the `--lang` argument when running the script. e.g. `python run.py --lang en --episode 1`

Limitation: when switching from a language to another, the `cache/ep##/video` directory has to be deleted. <br/>
Note for advanced users: length of some video shots differs, the script does not overwrite the generated video shot. It would be possible but is not a priority.
