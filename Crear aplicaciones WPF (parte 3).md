# Crear aplicaciones WPF (parte 3)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/07/10/crear-aplicaciones-wpf-parte-3/
```PowerShell
Add-Type -AssemblyName PresentationFramework
  
$codigoxaml = @'
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Mi primer ejemplo WPF" Height="100" Width="300">
    <Grid>
        <TextBlock Text="Hola"
                   HorizontalAlignment="Center"
                   VerticalAlignment="Center"
                   FontSize="10"
                   RenderTransformOrigin="0.5,0.5"
                   FontWeight="Bold">
            <TextBlock.RenderTransform>
                <TransformGroup>
                    <ScaleTransform ScaleX="1.25" ScaleY="4" />
                    <RotateTransform Angle="-15" />
                </TransformGroup>
            </TextBlock.RenderTransform>
        </TextBlock>
    </Grid>
</Window>
'@

$cargar = [System.XML.XMLReader]::Create([System.IO.StringReader]$codigoxaml)
$ventana = [System.Windows.Markup.XAMLReader]::Load($cargar)
$ventana.ShowDialog()

```
