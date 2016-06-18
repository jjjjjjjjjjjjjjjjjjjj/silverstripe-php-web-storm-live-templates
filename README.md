# SilverStripe live templates
My collection of live templates for IntelliJ PHP/WebStorm following PSR-2, using PHPDoc, and utilizing PHP 5.4 array shorthand syntax. These templates do not attempt cover every static nor function, but are a collection of snippets that I frequently use in my daily work. Feel free to [open issues](https://github.com/janneklouman/silverstripe-phpstorm-live-templates/issues) to suggest additional templates.

# Installation
Download and place the template files inside your IDE's templates folder. Where the folder is located depends on the version and type of IDE you are using. 

See [this IntelliJ article](https://intellij-support.jetbrains.com/hc/en-us/articles/206544519-Directories-used-by-the-IDE-to-store-settings-caches-plugins-and-logs) on where your settings are stored.


If you're lazy and you have PhpStorm2016.1 and wget installed, you can copy and paste the following and then restart your IDE:
### Mac OSX
```
cd ~/Library/Preferences/PhpStorm2016.1/templates/
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Fields.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Functions.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Skeletons.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Static%20Variables.xml
```

### Windows
```
cd c:\Users\USER_NAME\.PhpStorm2016.1\templates\
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Fields.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Functions.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Skeletons.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Static%20Variables.xml
```

### Linux
```
cd ~/.PhpStorm2016.1/templates/
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Fields.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Functions.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Skeletons.xml
wget https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Static%20Variables.xml
```
# Usage
After installing, when editing a PHP file you can simply type in the short code for the live template and then hit the "Choose lookup Item Replace" keymap binding (`tab` by default). For example, typing in `aa` then hitting `tab`, would generate the following:
```PHP
/**
 * @var array
 */
private static $allowed_actions = [
    '$END$'
];
```

# List of available templates and their contents
## Fields
https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Fields.xml
### cbf (check box field)
```PHP
CheckboxField::create('$NAME$', $LABEL$)$END$
```
### df (date field)
```PHP
DateField::create('$NAME$', $LABEL$)$END$
```
### fg (field group)
```PHP
$FIELDNAME$ = FieldGroup::create(
    $LABEL$,
    [
        $FIELDS$
    ]
)$END$
```
### gf (grid field)
```PHP
GridField::create(
    '$NAME$',
    $LABEL$
    $this->$DATALIST$(),
    GridFieldConfig_$TYPE$::create()
)$END$
```
### lf (literal field)
```PHP
LiteralField::create('$NAME$', $LABEL$)$END$
```
### nf (numeric field)
```PHP
NumericField::create('$NAME$', $LABEL$)$END$
```
### tf (text field)
```PHP
TextField::create('$NAME$', $LABEL$)$END$
```
## Functions
https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Functions.xml
### gcms (get cms fields)
```PHP
/**
 * @return FieldList
 */
public function getCMSFields() {

    $fields = parent::getCMSFields();
    
    $END$

    return $fields;

}
```
### log
```PHP
SS_Log::log( print_r ( $END$, true ), SS_Log::WARN );
```
### t (translate)
```PHP
_t('$STRING$', '$DEFAULT$')$END$
```
### ucms (update cms fields)
```PHP
/**
 * @param FieldList $fields
 */
public function updateCMSFields(FieldList $fields) 
{
    $END$
}
```
## Skeletons
https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Skeletons.xml
### dofs (data object file start)
```PHP
/**
 * $DESCRIPTION$
 * @author $AUTHOR$
 * @package $PACKAGE$
 * @subpackage $SUBPACKAGE$
 */
class $CLASS$ extends DataObject
{
    $END$
}
```
### defs (data extension file start)
```PHP
/**
 * $DESCRIPTION$
 * @author $AUTHOR$
 * @package $PACKAGE$
 * @subpackage $SUBPACKAGE$
 */
class $CLASS$Extension extends DataExtension
{
    $END$
}
```
### efs (extension file start)
```PHP
/**
 * $DESCRIPTION$
 * @author $AUTHOR$
 * @package $PACKAGE$
 * @subpackage $SUBPACKAGE$
 */
class $CLASS$ extends Extension
{
    $END$
}
```
### pfs (page file start)
```PHP
/**
 * $DESCRIPTION$
 * @author $AUTHOR$
 * @package $PACKAGE$
 * @subpackage $SUBPACKAGE$
 */
class $CLASS$ extends Page
{
    $END$
}

class $CLASS$_Controller extends Page_Controller 
{
}
```
## Static variables
https://raw.githubusercontent.com/janneklouman/silverstripe-phpstorm-live-templates/master/SilverStripe%20PHP%20Static%20Variables.xml
### aa (allowed actions)
```PHP
/**
 * @var array
 */
private static $allowed_actions = [
    '$END$'
];
```
### bmm (belongs many-many)
```PHP
/**
 * @var array
 */
private static $belongs_many_many = [
    '$VAR$'  => '$END$'
];
```
### db (database)
```PHP
/**
 * @var array
 */
private static $db = [
    '$VAR$' => '$END$'
];
```
### hm (has many)
```PHP
/**
 * @var array
 */
private static $has_many = [
    '$VAR$'  => '$END$'
];
```
### ho (has one)
```PHP
/**
 * @var array
 */
private static $has_one = [
    '$VAR$'  => '$END$'
];
```
### mm (many many)
```PHP
/**
 * @var array
 */
private static $many_many = [
    '$VAR$'  => '$END$'
];
```
### mmef (many many extra fields)
```PHP
/**
 * @var array
 */
private static $many_many_extraFields = [
    '$RELATION$' => [
        '$NAME$' => '$TYPE$'
    ]
];

```
### sef (searchable fields)
```PHP
/**
 * @var array
 */
private static $searchable_fields = [
    $END$
];
```
### suf (summary fields)
```PHP
/**
 * @var array
 */
private static $summary_fields = [
    $END$
];
```
