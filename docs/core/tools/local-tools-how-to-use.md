---
title: '자습서: .NET Core 로컬 도구 설치 및 사용'
description: .NET 도구를 로컬 도구로 설치하고 사용하는 방법을 알아봅니다.
ms.date: 02/12/2020
ms.openlocfilehash: a4355886513040e2436bdbd87905e5baee2dd7a5
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156701"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a>자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용

**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전

이 자습서에서는 로컬 도구를 설치하고 사용하는 방법을 설명합니다. [이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)에서 만든 도구를 사용합니다.

## <a name="prerequisites"></a>사전 요구 사항

* [이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)를 완료합니다.
* .NET Core 2.1 런타임을 설치합니다.

  이 자습서에서는 .NET Core 2.1을 대상으로 하는 도구를 설치하고 사용하므로 해당 런타임이 머신에 설치되어 있어야 합니다. 2\.1 런타임을 설치하려면 [.NET Core 2.1 다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core/2.1)로 이동하여 **앱 실행 - 런타임** 열에서 런타임 설치 링크를 찾습니다.

## <a name="create-a-manifest-file"></a>매니페스트 파일 만들기

로컬 액세스 전용(현재 디렉터리 및 하위 디렉터리용) 도구를 설치하려면 매니페스트 파일에 추가해야 합니다.

*microsoft.botsay* 폴더에서 한 수준 위인 *repository* 폴더로 이동합니다.

```console
cd ..
```

[dotnet new](dotnet-new.md) 명령을 실행하여 매니페스트 파일을 만듭니다.

```dotnetcli
dotnet new tool-manifest
```

출력은 파일을 성공적으로 생성했음을 나타냅니다.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

*.config/dotnet-tools.json* 파일에 아직 도구가 없습니다.

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

매니페스트 파일에 나열된 도구는 현재 디렉터리와 하위 디렉터리에서 사용할 수 있습니다. 현재 디렉터리는 매니페스트 파일이 있는 *.config* 디렉터리를 포함하는 디렉터리입니다.

로컬 도구를 참조하는 CLI 명령을 사용하는 경우 SDK는 현재 디렉터리와 부모 디렉터리에서 매니페스트 파일을 검색합니다. 매니페스트 파일을 찾았지만 파일이 참조된 도구를 포함하지 않는 경우 부모 디렉터리까지 검색을 계속합니다. 참조된 도구를 찾거나 `isRoot`가 `true`로 설정된 매니페스트 파일을 찾으면 검색이 종료됩니다.

## <a name="install-botsay-as-a-local-tool"></a>로컬 도구로 botsay 설치

첫 번째 자습서에서 만든 패키지에서 도구를 설치합니다.

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

이 명령은 이전 단계에서 만든 매니페스트 파일에 도구를 추가합니다. 명령 출력에는 새로 설치된 도구가 있는 매니페스트 파일이 표시됩니다.

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

이제 *.config/dotnet-tools.json* 파일에 도구가 하나 있습니다.

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a>도구 사용

*repository* 폴더에서 `dotnet tool run` 명령을 실행하여 도구를 호출합니다.

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>다른 사용자가 설치한 로컬 도구 복원

일반적으로 로컬 도구는 리포지토리의 루트 디렉터리에 설치합니다. 매니페스트 파일을 리포지토리에 체크 인하면 다른 개발자가 최신 매니페스트 파일을 가져올 수 있습니다. 매니페스트 파일에 나열된 모든 도구를 설치하기 위해 단일 `dotnet tool restore` 명령을 실행할 수 있습니다.

1. *.config/dotnet-tools.json* 파일을 열고 내용을 다음 JSON으로 바꿉니다.

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. `<name>`을 프로젝트를 만드는 데 사용한 이름으로 바꿉니다.

1. 변경 내용을 저장합니다.

   이러한 변경을 수행하는 것은 다른 사용자가 프로젝트 디렉터리에 대한 패키지 `dotnetsay`를 설치한 후 리포지토리의 최신 버전을 가져오는 것과 같습니다.

1. `dotnet tool restore` 명령을 실행합니다.

   ```dotnetcli
   dotnet tool restore
   ```

   이 명령은 다음 예제와 같은 출력을 생성합니다.

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. 도구를 사용할 수 있는지 확인합니다.

   ```dotnetcli
   dotnet tool list
   ```

   출력은 다음 예제와 같은 패키지 및 명령 목록입니다.

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. 도구를 테스트합니다.

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a>로컬 도구 업데이트

로컬 도구 `dotnetsay`의 설치된 버전은 2.1.3입니다.  최신 버전은 2.1.4입니다. [dotnet tool update](dotnet-tool-update.md) 명령을 사용하여 도구를 최신 버전으로 업데이트합니다.

```dotnetcli
dotnet tool update dotnetsay
```

출력은 새 버전 번호를 나타냅니다.

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

이 업데이트 명령은 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾아 업데이트합니다. 검색 범위에 있는 매니페스트 파일에 이러한 패키지 ID가 없는 경우 SDK는 가장 가까운 매니페스트 파일에 새 항목을 추가합니다. `isRoot = true`로 설정된 매니페스트 파일을 찾을 때까지 검색 범위는 부모 디렉터리까지 포함합니다.

## <a name="remove-local-tools"></a>로컬 도구 제거

[dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 실행하여 설치된 도구를 제거합니다.

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>문제 해결

자습서를 수행하는 동안 오류 메시지가 표시되는 경우 [.NET Core 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.

## <a name="see-also"></a>참조

자세한 내용은 [.NET Core 도구](global-tools.md)를 참조하세요.
