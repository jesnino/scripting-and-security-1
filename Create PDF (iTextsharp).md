# Create PDF (iTextsharp)
## PowerShell 
### URL: https://www.jesusninoc.com/2015/07/05/create-pdf-itextsharp/
```PowerShell
#Download https://sourceforge.net/projects/itextsharp/

[System.Reflection.Assembly]::LoadFrom("F:\power\PowerShell.PDF\itextsharp.dll")

$document=New-Object itextsharp.text.document
$stream=[IO.File]::OpenWrite("F:\power\output.pdf")
[itextsharp.text.pdf.PdfWriter]::GetInstance($document, $stream)

$document.Open()
Get-Content F:\power\documentread.txt | %{
$line=New-Object itextsharp.text.Paragraph($_)
$document.Add($line)
}

$document.Close()
$stream.Close()

```
