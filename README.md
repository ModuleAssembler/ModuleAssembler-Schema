# ModuleAssembler Schema

JSON Schema for Module Assembler configuration data file named **moduleproject.json**

## Schema Properties

| Property | Type | Required | Valid Values (`default`) | Description |
| --- | --- | --- | --- | --- |
| ProjectName | `string` | yes | | Name of the module project. |
| Description | `string` | yes | | Description of the functionality provided by this module. |
| Version | `string` | yes | | Version number of this module, use Semantic Versioning. |
| CopyResourcesToModuleRoot | `boolean` | no | true, `false` | Specifies if resource files will be placed in the built module's root directory, instead of in a resources subfolder. |
| Manifest | `object` | yes | | PowerShell Module Manifest Configuration Items. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Author | `string` | yes | | Author of this module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CompanyName | `string` | no | | Company or vendor of this module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;PowerShellVersion | `string` | yes | | Minimum version of the PowerShell engine required by this module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GUID | `string` | yes | | ID used to uniquely identify this module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Tags | `array[string]` | no | | Tags applied to this module. These help with module discovery in online galleries. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ProjectUri | `string` | no | | A URL to the main website for this project. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;LicenseUri | `string` | no | | A URL to the license for this project. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IconUri | `string` | no | | A URL to an icon representing this module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;RequiredModules | `array` | no | | Modules that must be imported into the global environment. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ModuleName | `string` | yes | | The required module name. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GUID | `string` | no | | GUID of the required module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ModuleVersion | `string` | no | | Minimum acceptable version of the required module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MaximumVersion | `string` | no | | Maximum acceptable version of the required module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;RequiredVersion | `string` | no | | Exact version of the required module. If specified then ModuleVersion and MaximumVersion can't be used. |
| Pester | `object` | no | | Pester Configuration Items. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CodeCoverage | `object` | no | | Code Coverage Configuration. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Enabled | `boolean` | yes | true, `false` | Enable Code Coverage. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OutputFormat | `string` | no | `JaCoCo`, CoverageGutters, Cobertura | Format to use for code coverage report. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CoveragePercentTarget | `number` | no | 0 - 100, `75` | Target percent of code coverage that you want to achieve. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TestResult | `object` | no | | Test Result Configuration. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Enabled | `boolean` | yes | `true`, false | Enable Test Results. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OutputFormat | `string` | no | NUnitXml, NUnit2.5, NUnit3, `JUnitXml` | Format to use for test result report. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Output | `object` | no | | Output Configuration. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Verbosity | `string` | yes | None, Normal, `Detailed`, Diagnostic | The verbosity of output. |
