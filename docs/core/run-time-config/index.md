---
title: 런타임 구성
description: 런타임 구성 설정을 사용하여 .NET Core 애플리케이션을 구성하는 방법을 알아봅니다.
ms.date: 11/13/2019
ms.openlocfilehash: 2665026347e94d26026821beb2bfcf8441f755f6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801923"
---
# <a name="net-core-run-time-configuration-settings"></a>.NET Core 런타임 구성 설정

.NET Core에서는 구성 파일 및 환경 변수를 사용하여 런타임에 .NET Core 애플리케이션의 동작을 구성할 수 있도록 지원합니다. 런타임 구성은 다음과 같은 경우에 유용한 옵션입니다.

- 애플리케이션의 소스 코드를 소유하거나 제어하지 않으므로 프로그래밍 방식으로 해당 소스 코드를 구성할 수 없습니다.

- 애플리케이션의 여러 인스턴스가 단일 시스템에서 동시에 실행되며 최적의 성능을 위해 각 인스턴스를 구성하려고 합니다.

> [!NOTE]
> 이 설명서는 진행 중인 작업입니다. 여기에 제공된 정보가 불완전하거나 부정확한 경우에는 [이슈를 열어](https://github.com/dotnet/docs/issues) 그에 대해 알려주시거나 [끌어오기 요청을 제출](https://github.com/dotnet/docs/pulls)하여 이슈를 해결하세요. dotnet/docs 리포지토리에 대한 끌어오기 요청 제출에 대한 자세한 내용은 [기여자 가이드](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)를 참조하세요.

.NET Core는 런타임에 애플리케이션을 구성하는 다음과 같은 메커니즘을 제공합니다.

- [runtimeconfig.json 파일](#runtimeconfigjson)

- [환경 변수](#environment-variables)

설명서의 이 섹션에 포함된 문서는 디버깅 및 가비지 수집 같은 범주별로 구성되어 있습니다. 사용 가능한 구성 옵션은 *runtimeconfig.json*(.NET Core에만 해당), *app.config*(.NET Framework에만 해당) 및 환경 변수에 대해 표시되어 있습니다.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

앱의 *runtimeconfig.json* 파일의 **configProperties** 섹션에 런타임 구성 옵션을 지정합니다. 이 섹션은 형식은 다음과 같습니다.

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

예제 파일은 다음과 같습니다.

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

*runtimeconfig.json* 파일은 [dotnet build](../tools/dotnet-build.md) 명령에 의해 빌드 디렉터리에 자동으로 만들어집니다. Visual Studio에서 **빌드** 메뉴 옵션을 선택하는 경우에도 만들어집니다. 그러면 파일이 만들어진 후 편집할 수 있습니다.

일부 구성 값은 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 설정할 수도 있습니다.

## <a name="environment-variables"></a>환경 변수

환경 변수를 사용하여 일부 런타임 구성 정보를 제공할 수 있습니다. 환경 변수로 지정된 구성 노브는 일반적으로 **COMPlus_** 접두사가 붙어 있습니다.

Windows 제어판, 명령줄 또는 Windows 및 Unix 기반 시스템에서 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 환경 변수를 정의할 수 있습니다.

다음 예제는 명령줄에서 환경 변수를 설정하는 방법을 보여 줍니다.

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
