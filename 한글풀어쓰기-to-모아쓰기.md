macOS에서 작성한 파일 이름은 풀어쓰기 형식으로 저장된다.  
이를 모아쓰기로 변환하는 powershell 명령이다.

```powershell
Get-ChildItem -Recurse | % { $n=$_.Name.Normalize([Text.NormalizationForm]::FormC); if ($_.Name -ne $n) { Rename-Item -LiteralPath $_.FullName -NewName $n } }
```
