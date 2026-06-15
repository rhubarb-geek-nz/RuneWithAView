# rhubarb-geek-nz.RuneWithAView
[PowerShell](https://learn.microsoft.com/en-us/powershell/scripting/overview) module providing a view formatter for [System.Text.Rune](https://learn.microsoft.com/en-us/dotnet/fundamentals/runtime-libraries/system-text-rune)

Install from [PSGallery](https://www.powershellgallery.com/packages/rhubarb-geek-nz.RuneWithAView/1.0.0) with

```
PS> Install-Module rhubarb-geek-nz.RuneWithAView
```

Import into running process with

```
PS> Import-Module rhubarb-geek-nz.RuneWithAView
```

Show the installed views

```
PS> Get-FormatData -TypeName System.Text.Rune

TypeNames          FormatViewDefinition
---------          --------------------
{System.Text.Rune} {RuneWithAView, RuneWithAView, RuneWithAView}
```

Example list view, equivalent to piping through Format-List

```
PS> "A`r`u{2211}`u{1F600}".EnumerateRunes()

ToString : A
Value    : 0x41

ToString : •
Value    : 0xD

ToString : ∑
Value    : 0x2211

ToString : 😀
Value    : 0x1F600
```

Example table

```
PS> "A`r`u{2211}`u{1F600}".EnumerateRunes() | Format-Table

ToString Value
-------- -----
A        0x41
•        0xD
∑        0x2211
😀       0x1F600
```

Example wide listing

```
PS> "A`r`u{2211}`u{1F600}".EnumerateRunes() | Format-Wide

A 0x41                                                                   • 0xD
∑ 0x2211                                                                 😀 0x1F600
```
