---
title: 트리밍 옵션
description: 자체 포함 앱의 트리밍을 제어하는 방법을 알아봅니다.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 42e98f9ede004f06221d2df5ecd076500061e37d
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465418"
---
# <a name="trimming-options"></a>트리밍 옵션

다음 MSBuild 속성 및 항목은 [트리밍된 자체 포함 배포](trim-self-contained.md)의 동작에 영향을 줍니다. 일부 옵션에는 트리밍을 구현하는 기본 도구의 이름인 `ILLink`가 언급됩니다. `ILLink` 명령줄 도구에 관한 자세한 내용은 [illink 옵션](https://github.com/mono/linker/blob/master/docs/illink-options.md)을 참조하세요.

## <a name="enable-trimming"></a>트리밍 사용

- `<PublishTrimmed>true</PublishTrimmed>`

   SDK에서 정의한 기본 설정을 사용하여 게시 중에 트리밍을 사용합니다.

`Microsoft.NET.Sdk`를 사용하는 경우 netcoreapp 런타임 팩에서 프레임워크 어셈블리의 어셈블리 수준 트리밍을 수행합니다. 애플리케이션 코드와 프레임워크가 아닌 라이브러리는 트리밍되지 않습니다. 다른 SDK는 서로 다른 기본값을 정의할 수 있습니다.

## <a name="trimming-granularity"></a>트리밍 세분성

다음 세분성 설정은 적극적으로 사용되지 않는 IL을 삭제하는 방법을 제어합니다. 해당 항목은 속성으로 설정하거나 [개별 어셈블리](#trimmed-assemblies)에서 메타데이터로 설정할 수 있습니다.

- `<TrimMode>copyused</TrimMode>`

   어셈블리 수준 트리밍을 사용하면 어셈블리의 일부가 정적으로 인식되는 방식으로 사용되는 경우 전체 어셈블리가 유지됩니다.

- `<TrimMode>link</TrimMode>`

    멤버 수준 트리밍을 사용하면 형식에서 사용되지 않는 멤버가 제거됩니다.

`<IsTrimmable>true</IsTrimmable>` 메타데이터가 있지만 명시적 `TrimMode`가 없는 어셈블리는 전역 `TrimMode`를 사용합니다. `Microsoft.NET.Sdk`의 기본값 `TrimMode`는 `copyused`입니다.

## <a name="trimmed-assemblies"></a>트리밍된 어셈블리

트리밍된 앱을 게시하면 SDK는 트리밍을 위해 처리할 파일 세트를 나타내는 `ManagedAssemblyToLink`라는 `ItemGroup`을 계산합니다. `ManagedAssemblyToLink`에는 어셈블리별로 트리밍 동작을 제어하는 메타데이터가 있을 수 있습니다. 해당 메타데이터를 설정하려면 기본 제공 `PrepareForILLink` 대상 전에 실행되는 대상을 만듭니다. 다음 예제에서는 `MyAssembly` 트리밍을 사용하도록 설정하는 방법을 보여 줍니다.

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

SDK는 게시 중에 해당 세트를 계산하고 변경하지 않을 것으로 예상하기 때문에 `ManagedAssemblyToLink`에서 항목을 추가하거나 제거하지 마세요. 지원되는 메타데이터는 다음과 같습니다.

- `<IsTrimmable>true</IsTrimmable>`

  지정된 어셈블리가 트리밍되는지 여부를 제어합니다.

- `<TrimMode>copyused</TrimMode>` 또는 `<TrimMode>link</TrimMode>`

  해당 어셈블리의 [트리밍 세분성](#trimming-granularity)을 제어합니다. 이 옵션은 전역 `TrimMode`보다 우선합니다. 어셈블리에서 `TrimMode`를 설정하는 것은 `<IsTrimmable>true</IsTrimmable>`을 의미합니다.

## <a name="root-assemblies"></a>루트 어셈블리

`<IsTrimmable>true</IsTrimmable>`이 없는 모든 어셈블리는 분석의 루트로 고려됩니다. 즉, 모든 어셈블리와 정적으로 인식되는 모든 종속성이 유지됩니다. 추가 어셈블리는 이름(`.dll` 확장명이 없음)으로 “루트로 지정” 될 수 있습니다.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a>루트 설명자

분석을 위한 루트를 지정하는 또 다른 방법은 링커 [설명자 형식](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format)을 사용하는 XML 파일을 사용하는 것입니다. 이렇게 하면 전체 어셈블리가 아닌 특정 멤버를 루트로 지정할 수 있습니다.

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

예를 들어 `MyRoots.xml`은 애플리케이션에서 동적으로 액세스하는 특정 메서드를 루트로 지정할 수 있습니다.

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a>분석 경고

트리밍은 정적으로 연결할 수 없는 IL을 제거합니다. 리플렉션을 사용하는 앱 또는 동적 종속성을 만드는 다른 패턴은 트리밍을 통해 중단될 수 있습니다. 해당 패턴에 관해 경고하려면:

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    트리밍 분석 경고를 사용합니다.

여기에는 고유한 코드, 라이브러리 코드 및 프레임워크 코드를 비롯한 전체 앱에 관한 경고가 포함됩니다.

## <a name="warning-versions"></a>경고 버전

트리밍 분석은 SDK에서 분석 경고 버전을 제어하는 [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) 속성을 적용합니다. 트리밍 분석 경고의 버전을 독립적으로 제어하는 또 다른 속성이 있습니다(컴파일러의 `WarningLevel`과 비슷함).

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    지정된 수준 이하의 경고만 내보냅니다. 모든 경고 버전을 포함하려면 `9999`로 설정할 수 있습니다.

## <a name="suppressing-warnings"></a>경고 표시 안 함

`NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` 및 `TreatWarningsAsErrors`를 포함하여 도구 체인에서 적용하는 일반적인 MSBuild 속성을 사용하여 개별 [경고 코드](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes)를 표시하지 않을 수 있습니다. ILLink 오류로 경고 동작을 독립적으로 제어하는 추가 옵션이 있습니다.

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    ILLink 경고를 오류로 처리하지 마세요. 이렇게 하면 전역으로 컴파일러 경고를 오류로 처리할 때 트리밍 분석 경고를 오류로 전환하지 않을 수 있습니다.

## <a name="removing-symbols"></a>기호 제거

기호는 일반적으로 어셈블리와 일치하도록 트리밍됩니다. 모든 기호를 제거할 수도 있습니다.

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    포함된 PDB 및 별도 PDB 파일을 포함하여 트리밍된 애플리케이션에서 기호를 제거합니다. 이는 애플리케이션 코드 및 기호와 함께 제공되는 모든 종속성 둘 다에 다 적용됩니다.

SDK를 사용하여 `DebuggerSupport` 속성을 통해 디버거 지원을 사용하지 않도록 설정할 수도 있습니다. 디버거 지원이 사용되지 않으면 트리밍은 기호를 자동으로 제거합니다(`TrimmerRemoveSymbols`가 기본적으로 true로 설정됨).
