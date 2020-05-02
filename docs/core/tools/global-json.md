---
title: global.json 개요
description: .NET Core CLI 명령을 실행할 때 global.json 파일을 사용하여 .NET Core SDK 버전을 설정하는 방법에 대해 알아보세요.
ms.date: 04/21/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 5384b59cccb629a5409d26a8df7c81b3999fc95f
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021344"
---
# <a name="globaljson-overview"></a>global.json 개요

**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전

*global.json* 파일을 사용하면 .NET Core CLI 명령을 실행할 때 어떤 .NET Core SDK 버전을 사용할지 정의할 수 있습니다. .NET Core SDK를 선택하는 것은 프로젝트가 대상으로 하는 런타임을 지정하는 것과는 별개입니다. .NET Core SDK 버전은 사용된 .NET Core CLI 버전을 나타냅니다.

일반적으로 최신 버전의 SDK Tools를 사용하려고 하기 때문에 *global.json* 파일이 필요하지 않습니다. 일부 고급 시나리오에서는 SDK Tools의 버전을 컨트롤하는 것이 좋습니다. 이 문서에서는 해당 방법을 설명합니다.

대신 런타임 지정에 대한 자세한 내용은 [대상 프레임워크](../../standard/frameworks.md)를 참조하세요.

.NET Core SDK는 현재 작업 디렉터리(반드시 프로젝트 디렉터리와 동일하지는 않음) 또는 상위 디렉터리 중 하나에서 *global.json* 파일을 찾습니다.

## <a name="globaljson-schema"></a>global.json 스키마

### <a name="sdk"></a>sdk

형식: `object`

선택할 .NET Core SDK에 대한 정보를 지정합니다.

#### <a name="version"></a>버전

- 형식: `string`

- .NET Core 1.0 SDK부터 사용할 수 있습니다.

사용할 .NET Core SDK의 버전입니다.

이 필드:

- 와일드카드를 지원하지 않습니다. 즉, 전체 버전 번호가 지정되어야 합니다.
- 버전 범위를 지원하지 않습니다.

#### <a name="allowprerelease"></a>시험판 허용

- 형식: `boolean`

- .NET Core 3.0 SDK부터 사용할 수 있습니다.

사용할 SDK 버전을 선택할 때 SDK 확인자가 시험판 버전을 고려해야 하는지 여부를 나타냅니다.

이 값을 명시적으로 설정하지 않은 경우 Visual Studio에서 실행하고 있는지에 따라 기본값이 달라집니다.

- Visual Studio에서 실행하지 **않는** 경우 기본값은 `true`입니다.
- Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다. 즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 기본값은 `true`이고, 그렇지 않으면 `false`입니다.

#### <a name="rollforward"></a>롤포워드

- 형식: `string`

- .NET Core 3.0 SDK부터 사용할 수 있습니다.

SDK 버전을 선택할 때, 특정 SDK 버전이 누락된 경우 대체하거나 상위 버전을 사용하기 위한 지시문으로 사용할 롤포워드 정책입니다. 버전을 `latestMajor`로 설정하지 않는 한 `rollForward` 값을 사용하여 [버전](#version)을 지정해야 합니다.

사용 가능한 정책 및 해당 동작을 이해하려면 `x.y.znn` 형식의 SDK 버전에 대한 다음 정의를 참조하세요.

- `x`는 주 버전입니다.
- `y`는 부 버전입니다.
- `z`는 기능 밴드입니다.
- `nn`은 패치 버전입니다.

다음 표에서는 `rollForward` 키에 사용할 수 있는 값을 보여 줍니다.

| 값         | 동작 |
| ------------- | ---------- |
| `patch`       | 지정한 버전을 사용합니다. <br> 버전이 없으면 최신 패치 수준으로 롤포워드하세요. <br> 찾을 수 없으면 실패합니다. <br><br> 이 값은 이전 버전의 SDK에서 발생하는 레거시 동작입니다. |
| `feature`     | 지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `minor`       | 지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `major`       | 지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다. <br> 최신 패치 수준을 찾을 수 없는 경우 다음 상위 주 버전, 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `latestPatch` | 요청된 주 버전, 부 버전 및 기능 밴드와 패치 수준이 일치하고 지정된 값과 같거나 큰 최신 설치된 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `latestFeature` | 요청된 주 버전과 부 버전이 지정된 값과 같거나 큰 기능 밴드와 일치하는 설치된 최상위 기능 밴드와 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `latestMinor` | 요청된 주 버전이 지정된 값보다 크거나 같은 부 버전과 일치하는 최상위 부 버전, 기능 밴드 및 패치 수준을 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `latestMajor` | 지정된 값보다 크거나 같은 주 버전과 함께 최상위 .Net Core SDK를 사용합니다. <br> 찾을 수 없으면 실패합니다. |
| `disable`     | 롤포워드하지 않습니다. 정확하게 일치해야 합니다. |

## <a name="examples"></a>예

다음 예제에서는 시험판 버전을 사용하지 않는 방법을 보여줍니다.

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

다음 예제에서는 지정된 버전과 같거나 높은 최상위 버전을 사용하는 방법을 보여줍니다.

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestMajor"
  }
}
```

다음 예제에서는 정확하게 지정된 버전을 사용하는 방법을 보여줍니다.

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

다음 예제에서는 설치된 특정 주 버전과 부 버전의 최신 기능 밴드 및 패치 버전을 사용하는 방법을 보여줍니다.

```json
{
  "sdk": {
    "version": "3.1.000",
    "rollForward": "latestFeature"
  }
}
```

다음 예제에서는 지정된 버전(3.1.1xx 형식)으로 설치된 최상위 패치 버전을 사용하는 방법을 보여줍니다.

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json 및 .NET Core CLI

*global json* 파일에 버전을 설정하기 위해서는 컴퓨터에 설치된 SDK 버전을 알고 있는 것이 좋습니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [.NET Core가 이미 설치되어 있는지 확인하는 방법](../install/how-to-detect-installed-versions.md#check-sdk-versions)을 참조하세요.

컴퓨터에 추가 .NET Core SDK 버전을 설치하려면 [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지를 방문하세요.

다음 예제와 비슷한 [dotnet new](dotnet-new.md) 명령을 실행하여 현재 디렉터리에서 *global.json* 파일을 새로 만들 수 있습니다.

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a>일치 규칙

> [!NOTE]
> 일치 규칙은 설치된 모든 .NET Core 설치 런타임에서 공통으로 사용되는 `dotnet.exe` 진입점에 의해 관리됩니다. 여러 개의 런타임이 나란히 설치된 경우 최신 버전의 .NET Corea Runtime에 대한 일치하는 규칙이 사용됩니다.

## <a name="net-core-3x"></a>[.NET Core 3.x](#tab/netcore3x)

.NET Core 3.0부터는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.

- *global. json* 파일을 찾을 수 없거나 *global.json*이 SDK 버전 또는 `allowPrerelease` 값을 지정하지 않은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`을 `latestMajor`로 설정하는 것과 같음). 시험판 SDK 버전을 고려하는지는 `dotnet`을 호출하는 방법에 따라 달라집니다.
  - Visual Studio에서 실행하지 **않는** 경우 시험판 버전이 고려됩니다.
  - Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다. 즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK의 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 시험판 버전이 고려됩니다. 그렇지 않으면 릴리스 버전만 고려됩니다.
- SDK 버전을 지정하지 않고 `allowPrerelease` 값을 지정하는 *global.json* 파일을 찾은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`를 `latestMajor`로 설정하는 것과 같음). 최신 SDK 버전을 릴리스 또는 시험판이 될 수 있는지는 `allowPrerelease` 값에 따라 달라집니다. `true`는 시험판 버전이 고려됨을 나타냅니다. `false`는 릴리스 버전만 고려됨을 나타냅니다.
- *global.json* 파일을 찾아 SDK 버전을 지정하는 경우 다음과 같습니다.

  - `rollFoward` 값이 설정되지 않은 경우 `latestPatch`를 기본 `rollForward` 정책으로 사용합니다. 그렇지 않으면 [롤포워드](#rollforward) 섹션에서 각 값과 해당 동작을 확인하세요.
  - 시험판 버전을 고려하는지와 `allowPrerelease`가 설정되지 않은 경우의 기본 동작은 [allowPrerelease](#allowprerelease) 섹션에 설명되어 있습니다.

## <a name="net-core-2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x SDK에서는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.

- *global.json* 파일이 없거나 *global.json*이 SDK 버전을 지정하지 않으면 최신 설치된 SDK 버전이 사용됩니다. 최신 SDK 버전은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다.
- *global.json*이 SDK 버전을 지정하는 경우
  - 지정된 SDK 버전이 머신에서 발견되면 정확한 버전이 사용됩니다.
  - 지정된 SDK 버전이 시스템에서 발견되지 않으면 해당 버전의 최신 **패치 버전**이 사용됩니다. 설치된 최신 SDK **패치 버전**은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다. .NET Core 2.1 이상에서는 지정된 **패치 버전**보다 낮은 **패치 버전**은 SDK 선택에서 무시됩니다.
  - 지정된 SDK 버전과 적절한 SDK **패치 버전**을 찾을 수 없으면 오류가 발생합니다.

SDK 버전은 다음과 같은 부분으로 구성됩니다.

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

.NET Core SDK의 **기능 릴리스**는 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 첫 번째 자리(`x`)로 표시됩니다. 일반적으로 .NET Core SDK는 .NET Core보다 릴리스 주기가 빠릅니다.

**패치 버전**은 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 마지막 두 자리(`yz`)로 정의됩니다. 예를 들어, SDK 버전으로 `2.1.300`을 지정하면 SDK 선택은 최대 `2.1.399`까지 찾지만 `2.1.400`은 `2.1.300`의 패치 버전으로 간주되지 않습니다.

`2.1.100`부터 `2.1.201`까지의 .NET Core SDK 버전은 버전 번호 체계가 전환되는 중에 릴리스되었으며 `xyz` 표기법을 올바르게 처리하지 못합니다. *global.json* 파일에서 이 버전을 지정하면 지정된 버전이 대상 머신에 있는지 확인할 수 있도록 하는 것이 좋습니다.

---

## <a name="troubleshoot-build-warnings"></a>빌드 경고 문제 해결

* 다음 경고는 .NET Core SDK의 시험판 버전을 사용하여 프로젝트를 컴파일했음을 나타냅니다.

  > .NET Core SDK의 미리보기 버전으로 작업하고 있습니다. SDK 버전은 현재 프로젝트의 global.json 파일을 통해 정의할 수 있습니다. 자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=869452>를 참조하세요.

  .NET Core SDK 버전은 높은 품질의 기록과 약정을 가지고 있습니다. 그러나 시험판 버전을 사용하지 않으려면 [allowPrerelease](#allowprerelease) 섹션의 .NET Core 3.0 SDK 이상 버전에서 사용할 수 있는 다양한 전략을 확인하세요. .NET Core 3.0 이상 런타임 또는 SDK가 설치된 적이 없던 컴퓨터의 경우 *global.json* 파일을 만들고 사용할 정확한 버전을 지정해야 합니다.

* 다음 경고는 프로젝트가 .NET Core 2.1 SDK 이상 버전과 호환되지 않는 EF Core 1.0 또는 1.1을 대상으로 함을 나타냅니다.

  > 스타트업 프로젝트 '{startupProject}'는 '.NETCoreApp' 버전 '{targetFrameworkVersion}' 프레임워크를 대상으로 합니다. 이 버전의 Entity Framework Core .NET 명령줄 도구는 버전 2.0 이상만 지원합니다. 이전 버전의 도구 사용에 대한 자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=871254>를 참조하세요.

  .NET Core 2.1 SDK(버전 2.1.300)부터 `dotnet ef` 명령이 SDK에 포함되었습니다. 프로젝트를 컴파일하려면 머신에 .NET Core 2.0 SDK(버전 2.1.201) 또는 이전 버전을 설치하고 *global.json* 파일을 사용하여 원하는 SDK 버전을 정의하세요. `dotnet ef` 명령에 대한 자세한 내용은 [EF Core .NET 명령줄 도구](/ef/core/miscellaneous/cli/dotnet)를 참조하세요.

## <a name="see-also"></a>참조

- [프로젝트 SDK를 확인하는 방법](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
