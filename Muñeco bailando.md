# Muñeco bailando
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/16/muneco-bailando/
```PowerShell
$0=" ^ O ^`n  \|/ `n   |`n   | `n  / \ `n_/   \_"
$1="   O `n   | `n^--|--^`n   | `n   | `n __|__"
$2="   O `n   | `n^--|--^`n   | `n  / \ `n_/   \_"
for(1){$0,$1,$2 | %{$_;sleep -Milliseconds 500;cls}}

```
