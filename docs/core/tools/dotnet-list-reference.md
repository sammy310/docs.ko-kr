---
title: dotnet list reference 명령
description: dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802760"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet list reference` - 프로젝트 간 참조를 나열합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a>설명

`dotnet list reference` 명령은 지정한 프로젝트에 대해 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

* **`PROJECT`**

  작동할 프로젝트 파일입니다. 파일이 지정되지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.

## <a name="options"></a>옵션

* **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

* 지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* 현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.

  ```dotnetcli
  dotnet list reference
  ```
