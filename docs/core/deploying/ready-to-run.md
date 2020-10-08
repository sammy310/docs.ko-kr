---
title: ReadyToRun 배포 개요
description: ReadyToRun 배포의 정의와 .NET 5 및 .NET Core 3.0 이상 버전을 사용하여 앱을 게시하는 과정에서 사용을 고려해야 하는 이유를 알아봅니다.
author: davidwr
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: b4052a0c0f4ed9f6cfd273abe5ef45d018bd0ae0
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654950"
---
# <a name="readytorun-compilation"></a>ReadyToRun 컴파일

ReadyToRun(R2R) 형식으로 애플리케이션 어셈블리를 컴파일하면 .NET Core 애플리케이션의 시작 시간과 대기 시간을 개선할 수 있습니다. R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.

R2R 이진 파일은 애플리케이션이 로드될 때 JIT(Just-In-Time) 컴파일러에서 수행해야 하는 작업량을 줄여 시작 성능을 향상합니다. 이진 파일에는 JIT에서 생성되는 코드와 비슷한 네이티브 코드가 포함되어 있습니다. 그러나 R2R 이진 파일은 일부 시나리오에서 필요한 IL(중간 언어) 코드와 동일한 코드의 네이티브 버전을 모두 포함하므로 크기가 더 큽니다. R2R은 Linux x64 또는 Windows x64와 같은 특정 런타임 환경(RID)을 대상으로 하는 앱을 게시하는 경우에만 사용할 수 있습니다.

프로젝트를 ReadyToRun으로 컴파일하려면 PublishReadyToRun 속성을 true로 설정하여 애플리케이션을 게시해야 합니다.

앱을 ReadyToRun으로 게시하는 방법에는 두 가지가 있습니다.

01. PublishReadyToRun 플래그를 dotnet publish 명령에 직접 지정합니다. 자세한 내용은 [dotnet publish](../tools/dotnet-publish.md)를 참조하세요.

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. 프로젝트에서 속성을 지정합니다.

    - 프로젝트에 `<PublishReadyToRun>` 설정을 추가합니다.

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - 특수 매개 변수 없이 애플리케이션을 게시합니다.

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a>ReadyToRun 기능 사용의 영향

Ahead of Time 컴파일을 수행하면 애플리케이션 성능에 예측하기 어려운 복잡한 영향을 미칠 수 있습니다. 일반적으로 어셈블리의 크기가 2~3배 증가합니다. 파일의 실제 크기가 이렇게 증가하면 디스크에서 어셈블리를 로드하는 성능이 저하되고 프로세스의 작업 집합이 증가할 수 있습니다. 반면 런타임에 컴파일되는 메서드의 수는 일반적으로 크게 줄어듭니다. 결과적으로 코드의 양이 많은 대부분의 애플리케이션은 ReadyToRun을 사용하여 큰 성능상 이득을 얻을 수 있습니다. 코드의 양이 적은 애플리케이션은 .NET 런타임 라이브러리가 이미 ReadyToRun으로 미리 컴파일되어 있으므로 ReadyToRun 사용으로 성능이 크게 향상될 가능성이 적습니다.

여기서 설명하는 시작 개선은 애플리케이션 시작뿐 아니라 애플리케이션의 코드를 처음 사용할 때도 적용됩니다. 예를 들어 ReadyToRun을 사용하면 ASP.NET 애플리케이션에서 웹 API를 처음 사용할 때 응답 대기 시간을 줄일 수 있습니다.

### <a name="interaction-with-tiered-compilation"></a>계층화된 컴파일과의 상호 작용

미리 생성된 코드는 JIT에 의해 생성되는 코드만큼 고도로 최적화되어 있지 않습니다. 이 문제를 해결하기 위해 계층화된 컴파일은 일반적으로 사용되는 ReadyToRun 메서드를 JIT 생성 메서드로 바꿉니다.

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a>미리 컴파일되는 어셈블리 집합은 어떻게 선택되나요?

SDK는 애플리케이션과 함께 배포되는 어셈블리를 미리 컴파일합니다. 자체 포함 애플리케이션의 경우 이 어셈블리 집합에 프레임워크가 포함됩니다. C++/CLI 이진 파일은 ReadyToRun 컴파일에 적합하지 않습니다.

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a>미리 컴파일할 메서드 집합은 어떻게 선택되나요?

컴파일러는 최대한 많은 메서드를 미리 컴파일하려 시도합니다. 그러나 예상하지 못한 다양한 이유로 ReadyToRun 기능을 사용하면 JIT가 실행되지 않습니다.

이러한 이유에는 다음이 포함되지만 이에 국한되지 않습니다.

- 별도의 어셈블리에 정의된 제네릭 형식 사용
- 네이티브 코드와의 Interop
- 컴파일러가 입증할 수 없는 하드웨어 내장 함수는 대상 컴퓨터에서 안전하게 사용 가능
- 일부 비정상적인 IL 패턴
- 리플렉션을 통한 동적 메서드 생성 또는 LINQ

## <a name="cross-platformarchitecture-restrictions"></a>교차 플랫폼/아키텍처 제한 사항

일부 SDK 플랫폼의 경우 ReadyToRun 컴파일러는 다른 대상 플랫폼에 크로스 컴파일을 수행할 수 있습니다. 지원되는 컴파일 대상은 아래 표에 설명되어 있습니다.

| SDK 플랫폼 | 지원되는 대상 플랫폼 |
| ------------ | --------------------------- |
| Windows X64  | Windows X86, Windows X64, Windows ARM32, Windows ARM64 |
| Windows X86  | Windows X86, Windows ARM32 |
| Linux X64    | Linux X86, Linux X64, Linux ARM32, Linux ARM64 |
| Linux ARM32  | Linux ARM32 |
| Linux ARM64  | Linux ARM64 |
| macOS X64    | macOS X64 |
