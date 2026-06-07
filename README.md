# Сервер — однофайловый exe со встроенным рантаймом
dotnet publish PiServer/PiServer.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -o publish/server-win

# Клиент (WinForms) — тоже однофайловый exe
dotnet publish PiClient/PiClient.csproj -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -o publish/client-win
