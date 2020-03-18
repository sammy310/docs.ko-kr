---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77466110"
---

패키지 관리자 피드에 추가되는 패키지는 해킹 가능한 형식으로 명명됩니다(`{product}-{type}-{version}`).

- **product**\
설치할 .NET 제품의 유형입니다. 유효한 옵션은 다음과 같습니다.

  - dotnet
  - aspnetcore

- **type**\
SDK와 런타임 중 선택합니다. 유효한 옵션은 다음과 같습니다.

  - sdk
  - 런타임

- **version**\
설치한 SDK 또는 런타임의 버전입니다. 이 문서에서는 항상 지원되는 최신 버전에 대한 지침을 제공합니다. 유효한 옵션은 모든 릴리스된 버전입니다. 예:

  - 3.1
  - 3.0
  - 2.1

  다운로드하려는 SDK/런타임을 Linux 배포판에서 사용할 수 없을 수 있습니다. 지원되는 배포 목록은 [.NET Core 종속성 및 요구 사항](../dependencies.md?pivots=os-linux)을 참조하세요.

### <a name="examples"></a>예

- ASP.NET Core 3.1 런타임 설치: `aspnetcore-runtime-3.1`
- .NET Core 2.1 런타임 설치: `dotnet-runtime-2.1`
- .NET Core 3.0 SDK 설치: `dotnet-sdk-3.0`

### <a name="package-missing"></a>패키지가 없음

패키지-버전 조합이 작동하지 않는다면 사용할 수 없는 것입니다. 예를 들어, ASP.NET Core SDK는 존재하지 않습니다. SDK 구성 요소는 .NET Core SDK에 포함되어 있습니다. 값 `aspnetcore-sdk-2.2`는 올바르지 않으며, 올바른 값은 `dotnet-sdk-2.2`입니다. .NET Core에서 지원하는 Linux 배포 목록은 [.NET Core 종속성 및 요구 사항](../dependencies.md?pivots=os-linux)을 참조하세요.
