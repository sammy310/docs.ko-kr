---
title: dotnet nuget delete 명령
description: dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612630"
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.

## <a name="synopsis"></a>개요

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a>설명

`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다. [nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.

## <a name="arguments"></a>인수

* **`PACKAGE_NAME`**

  삭제할 패키지의 이름/ID입니다.

* **`PACKAGE_VERSION`**

  삭제할 패키지의 버전입니다.

## <a name="options"></a>옵션

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

* **`--force-english-output`**

  고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

* **`--interactive`**

  명령 차단을 허용하고 인증 등의 작업에 대해 수동 작업을 요구합니다. .NET Core 2.2 SDK 이후 사용할 수 있는 옵션입니다.

* **`-k|--api-key <API_KEY>`**

  서버에 대한 API 키입니다.

* **`--no-service-endpoint`**

  소스 URL에 “api/v2/package”를 추가하지 마세요. .NET Core 2.1 SDK 이후 사용할 수 있는 옵션입니다.

* **`--non-interactive`**

  사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.

* **`-s|--source <SOURCE>`**

  서버 URL을 지정합니다. nuget.org에 대해 지원되는 URL에는 `https://www.nuget.org`, `https://www.nuget.org/api/v3` 및 `https://www.nuget.org/api/v2/package`가 포함됩니다. 개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

* **`--force-english-output`**

  고정 영어 기반 문화권을 사용하여 애플리케이션을 강제로 실행합니다.

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

* **`-k|--api-key <API_KEY>`**

  서버에 대한 API 키입니다.

* **`--non-interactive`**

  사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.

* **`-s|--source <SOURCE>`**

  서버 URL을 지정합니다. nuget.org에 대해 지원되는 URL에는 `https://www.nuget.org`, `https://www.nuget.org/api/v3` 및 `https://www.nuget.org/api/v2/package`가 포함됩니다. 개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.

---

## <a name="examples"></a>예제

* `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* 사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```