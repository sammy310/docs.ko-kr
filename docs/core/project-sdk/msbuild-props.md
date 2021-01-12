---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET SDK에서 이해하는 MSBuild 속성 및 항목에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 27944a6726f8d74a3b00c7c774faa8037c0f2f0e
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899628"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a>.NET SDK 프로젝트용 MSBuild 참조

이 페이지는 .NET 프로젝트를 구성하는 데 사용할 수 있는 MSBuild 속성 및 항목에 대한 참조입니다.

> [!NOTE]
> 이 페이지는 진행 중인 작업이며 .NET SDK의 유용한 MSBuild 속성이 모두 나열된 것은 아닙니다. 일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.

## <a name="framework-properties"></a>프레임워크 속성

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

`TargetFramework` 속성은 앱의 대상 프레임워크 버전을 지정합니다. 유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.

### <a name="targetframeworks"></a>TargetFrameworks

앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다. 유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.

> [!NOTE]
> `TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> 이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다. `netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.

메타패키지 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다. 다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a>패키지 속성

`PackageId`, `PackageVersion`, `PackageIcon`, `Title`, `Description`과 같은 속성을 지정하여 프로젝트에서 생성되는 패키지를 설명할 수 있습니다. 이러한 속성 및 다른 속성에 대한 자세한 내용은 [팩 대상](/nuget/reference/msbuild-targets#pack-target)을 참조하세요.

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a>속성 및 항목 게시

- [CopyLocalLockFileAssemblies](#copylocallockfileassemblies)
- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="copylocallockfileassemblies"></a>CopyLocalLockFileAssemblies

`CopyLocalLockFileAssemblies` 속성은 다른 라이브러리에 대한 종속성이 있는 플러그 인 프로젝트에 유용합니다. 이 속성을 `true`로 설정하면 NuGet 패키지 종속성이 출력 디렉터리에 복사됩니다. 즉, `dotnet build`의 출력을 사용하여 모든 머신에서 플러그 인을 실행할 수 있습니다.

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> 또는 `dotnet publish`를 사용하여 클래스 라이브러리를 게시할 수 있습니다. 자세한 내용은 [dotnet publish](../tools/dotnet-publish.md)를 참조하세요.

### <a name="runtimeidentifier"></a>RuntimeIdentifier

`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다. RID를 통해 자체 포함 배포를 게시할 수 있습니다.

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다. 여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다. `RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.

> [!TIP]
> 단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

`TrimmerRootAssembly` 항목을 사용하면 [‘트리밍’](../deploying/trim-self-contained.md)에서 어셈블리를 제외할 수 있습니다. 트리밍은 패키지된 애플리케이션에서 런타임의 사용되지 않은 부분을 제거하는 프로세스입니다. 일부 경우에는 트리밍이 필요한 참조를 잘못 제거할 수 있습니다.

다음 XML은 트리밍에서 `System.Security` 어셈블리를 제외합니다.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a>UseAppHost

`UseAppHost` 속성은 배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다. 자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.

.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다. `UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

배포에 대한 자세한 내용은 [.NET 애플리케이션 배포](../deploying/index.md)를 참조하세요.

## <a name="compile-properties"></a>컴파일 속성

- [EmbeddedResourceUseDependentUponConvention](#embeddedresourceusedependentuponconvention)
- [LangVersion](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a>EmbeddedResourceUseDependentUponConvention

`EmbeddedResourceUseDependentUponConvention` 속성은 리소스 파일과 공동 배치된 소스 파일의 형식 정보에서 리소스 매니페스트 파일 이름을 생성할지 여부를 정의합니다. 예를 들어 *Form1.resx* 가 *Form1.cs* 와 동일한 폴더에 있고 `EmbeddedResourceUseDependentUponConvention`가 `true`로 설정된 경우 생성된 *.resources* 파일은 *Form1.cs* 에 정의된 첫 번째 형식에서 이름을 가져옵니다. 예를 들어 `MyNamespace.Form1`이 *Form1.cs* 에 정의된 첫 번째 형식이면 생성된 파일 이름은 *MyNamespace.Form1.resources* 입니다.

> [!NOTE]
> `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 `EmbeddedResource` 항목에 대해 지정된 경우 해당 리소스 파일에 대해 생성된 매니페스트 파일 이름은 이러한 메타데이터를 기반으로 합니다.

기본적으로 새 .NET 프로젝트에서 이 속성은 `true`로 설정됩니다. 이 속성이 `false`로 설정되고 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 *.resx* 파일의 상대 파일 경로를 기반으로 합니다. 자세한 내용은 [리소스 매니페스트 파일 이름이 지정되는 방식](../resources/manifest-file-names.md)을 참조하세요.

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a>LangVersion

`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다. 예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.

## <a name="code-analysis-properties"></a>코드 분석 속성

### <a name="analysislevel"></a>AnalysisLevel

`AnalysisLevel` 속성을 사용하여 코드 분석 수준을 지정할 수 있습니다. 예를 들어 코드 분석기를 미리 보기 위해 액세스하려면 `AnalysisLevel`을 `preview`로 설정합니다. 기본값은 `latest`입니다.

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

다음 표에 사용 가능한 옵션이 나와 있습니다.

| 값 | 의미 |
|-|-|
| `latest` | 릴리스된 최신 코드 분석기가 사용됩니다. 이것이 기본값입니다. |
| `preview` | 최신 코드 분석기는 미리 보기로 제공되는 경우에도 사용됩니다. |
| `5.0` | 최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다. |
| `5` | 최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다. |

### <a name="analysismode"></a>AnalysisMode

.NET 5.0부터 .NET SDK에는 모든 [“CA” 모드 품질 규칙](../../fundamentals/code-analysis/quality-rules/index.md)이 함께 제공됩니다. 기본적으로 [일부 규칙만 빌드 경고로 사용 설정](../../fundamentals/code-analysis/overview.md#enabled-rules)됩니다. `AnalysisMode` 속성을 사용하면 기본적으로 사용하도록 설정되는 규칙 집합을 사용자 지정할 수 있습니다. 더욱 적극적인(옵트아웃) 분석 모드나 더욱 보수적인(옵트인) 분석 모드로 전환할 수 있습니다. 예를 들어 기본적으로 모든 규칙을 빌드 경고로 사용하도록 설정하려는 경우 값을 `AllEnabledByDefault`로 설정합니다.

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

다음 표에 사용 가능한 옵션이 나와 있습니다.

| 값 | 의미 |
|-|-|
| `Default` | 특정 규칙이 빌드 경고로 사용되고, 다른 특정 규칙이 Visual Studio IDE 추천으로 사용되며, 나머지는 사용하지 않도록 설정되는 기본 모드입니다. |
| `AllEnabledByDefault` | 모든 규칙이 기본적으로 빌드 경고로 사용되는 적극적인(또는 옵트아웃) 모드입니다. 개별 규칙을 선택적으로 [옵트아웃](../../fundamentals/code-analysis/configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다. |
| `AllDisabledByDefault` | 모든 규칙이 기본적으로 사용하지 않도록 설정되는 보수적인(또는 옵트인) 모드입니다. 개별 규칙을 선택적으로 [옵트인](../../fundamentals/code-analysis/configuration-options.md)하여 사용하도록 설정할 수 있습니다. |

### <a name="codeanalysistreatwarningsaserrors"></a>CodeAnalysisTreatWarningsAsErrors

`CodeAnalysisTreatWarningsAsErrors` 속성을 사용하면 코드 품질 분석 경고(CAxxxx)를 경고로 처리할지 여부를 구성하고 빌드를 중단할 수 있습니다. 프로젝트를 빌드할 때 `-warnaserror` 플래그를 사용하면 [.NET 코드 품질 분석](../../fundamentals/code-analysis/overview.md#code-quality-analysis) 경고도 오류로 처리됩니다. 코드 품질 분석 경고를 오류로 처리하지 않으려는 경우 프로젝트 파일에서 `CodeAnalysisTreatWarningsAsErrors` MSBuild 속성을 `false`로 설정할 수 있습니다.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a>EnableNETAnalyzers

.NET 5.0 이상을 대상으로 하는 프로젝트의 경우 기본적으로 [.NET 코드 품질 분석](../../fundamentals/code-analysis/overview.md#code-quality-analysis)이 사용됩니다. `EnableNETAnalyzers` 속성을 `true`로 설정하여 이전 버전의 .NET을 대상으로 하는 프로젝트에서 .NET 코드 분석을 사용할 수 있습니다. 모든 프로젝트에서 코드 분석을 사용하지 않으려면 해당 속성을 `false`로 설정합니다.

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> .Net 5.0 이전 .NET 버전을 대상으로 하는 프로젝트에서 .NET 코드 분석을 사용할 수 있는 또 다른 방법은 [AnalysisLevel](#analysislevel) 속성을 `latest`로 설정하는 것입니다.

### <a name="enforcecodestyleinbuild"></a>EnforceCodeStyleInBuild

> [!NOTE]
> 이 기능은 현재 시험용으로 제공되며 .NET 5 릴리스와 .NET 6 릴리스 사이에 변경될 수 있습니다.

[.NET 코드 스타일 분석](../../fundamentals/code-analysis/overview.md#code-style-analysis)은 모든 .NET 프로젝트에 대해 빌드 시 기본적으로 사용하지 않도록 설정됩니다. `EnforceCodeStyleInBuild` 속성을 `true`로 설정하여 .NET 프로젝트에 대해 코드 스타일 분석을 사용하도록 설정할 수 있습니다.

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

경고 또는 오류로 [구성된](../../fundamentals/code-analysis/overview.md#code-style-analysis) 모든 코드 스타일 규칙은 빌드 및 보고 위반 시 실행됩니다.

## <a name="run-time-configuration-properties"></a>런타임 구성 속성

앱의 프로젝트 파일에서 MSBuild 속성을 지정하여 몇 가지 런타임 동작을 구성할 수 있습니다. 런타임 동작을 구성하는 다른 방법에 관한 내용은 [런타임 구성 설정](../run-time-config/index.md)을 참조하세요.

- [ConcurrentGarbageCollection](#concurrentgarbagecollection)
- [InvariantGlobalization](#invariantglobalization)
- [RetainVMGarbageCollection](#retainvmgarbagecollection)
- [ServerGarbageCollection](#servergarbagecollection)
- [ThreadPoolMaxThreads](#threadpoolmaxthreads)
- [ThreadPoolMinThreads](#threadpoolminthreads)
- [TieredCompilation](#tieredcompilation)
- [TieredCompilationQuickJit](#tieredcompilationquickjit)
- [TieredCompilationQuickJitForLoops](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a>ConcurrentGarbageCollection

`ConcurrentGarbageCollection` 속성은 [백그라운드(동시) 가비지 수집](../../standard/garbage-collection/background-gc.md)이 사용하도록 설정되었는지 여부를 구성합니다. 백그라운드 가비지 수집을 사용하지 않으려면 값을 `false`로 설정합니다. 자세한 내용은 [백그라운드 GC](../run-time-config/garbage-collector.md#background-gc)를 참조하세요.

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

`InvariantGlobalization` 속성은 앱이 문화권별 데이터에 액세스할 수 없는 ‘세계화 고정’ 모드에서 실행되는지 여부를 구성합니다. 세계화 고정 모드에서 실행하려면 값을 `true`로 설정합니다. 자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

`RetainVMGarbageCollection` 속성은 삭제된 메모리 세그먼트를 나중에 사용하기 위해 대기 목록에 넣거나 릴리스하도록 가비지 수집기를 구성합니다. 값을 `true`로 설정하여 가비지 수집기가 대기 목록에 세그먼트를 넣도록 지시합니다. 자세한 내용은 [VM 유지](../run-time-config/garbage-collector.md#retain-vm)를 참조하세요.

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

`ServerGarbageCollection` 속성은 애플리케이션이 [워크스테이션 가비지 수집 또는 서버 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 사용할지 여부를 구성합니다. 서버 가비지 수집을 사용하려면 값을 `true`로 설정합니다. 자세한 내용은 [워크스테이션과 서버 비교](../run-time-config/garbage-collector.md#workstation-vs-server)를 참조하세요.

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

`ThreadPoolMaxThreads` 속성은 작업자 스레드 풀의 최대 스레드 수를 구성합니다. 자세한 내용은 [최대 스레드](../run-time-config/threading.md#maximum-threads)를 참조하세요.

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

`ThreadPoolMinThreads` 속성은 작업자 스레드 풀의 최소 스레드 수를 구성합니다. 자세한 내용은 [최소 스레드](../run-time-config/threading.md#minimum-threads)를 참조하세요.

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a>TieredCompilation

`TieredCompilation` 속성은 JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다. 계층화된 컴파일을 사용하지 않으려면 값을 `false`로 설정합니다. 자세한 내용은 [계층화된 컴파일](../run-time-config/compilation.md#tiered-compilation)을 참조하세요.

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

`TieredCompilationQuickJit` 속성은 JIT 컴파일러가 빠른 JIT를 사용하는지 여부를 구성합니다. 빠른 JIT를 사용하지 않으려면 값을 `false`로 설정합니다. 자세한 내용은 [빠른 JIT](../run-time-config/compilation.md#quick-jit)를 참조하세요.

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

`TieredCompilationQuickJitForLoops` 속성은 JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다. 루프를 포함하는 메서드에서 빠른 JIT를 사용하려면 값을 `true`로 설정합니다. 자세한 내용은 [루프에 대한 빠른 JIT](../run-time-config/compilation.md#quick-jit-for-loops)를 참조하세요.

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a>참조 속성 및 항목

- [AssetTargetFallback](#assettargetfallback)
- [DisableImplicitFrameworkReferences](#disableimplicitframeworkreferences)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [참조](#reference)
- [복원 관련 속성](#restore-related-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

`AssetTargetFallback` 속성을 사용하여 프로젝트 참조 및 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다. 예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다. 참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.

`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-frameworks)으로 설정할 수 있습니다.

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a>DisableImplicitFrameworkReferences

`DisableImplicitFrameworkReferences` 속성은 .NET Core 3.0 이상 버전을 대상으로 하는 경우 암시적 `FrameworkReference` 항목을 제어합니다. .NET Core 2.1 또는 .NET Standard 2.0 이전 버전을 대상으로 하는 경우에는 메타패키지의 패키지에 대한 암시적 [PackageReference](#packagereference) 항목을 제어합니다. (메타패키지는 다른 패키지에 대한 종속성으로만 구성된 프레임워크 기반 패키지입니다.) 또한 이 속성은 .NET Framework를 대상으로 하는 경우 `System`, `System.Core` 등과 같은 암시적 참조도 제어 합니다.

암시적 `FrameworkReference` 또는 [PackageReference](#packagereference) 항목을 사용하지 않도록 설정하려면 이 속성을 `true`로 설정합니다. 이 속성을 `true`로 설정하면 필요한 프레임워크나 패키지에만 명시적 참조를 추가할 수 있습니다.

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

`PackageReference` 항목은 NuGet 패키지에 대한 참조를 정의합니다.

`Include` 특성은 패키지 ID를 지정합니다. `Version` 특성은 버전 또는 버전 범위를 지정합니다. 최소 버전, 최대 버전, 범위 또는 정확한 일치를 지정하는 방법에 대한 자세한 내용은 [버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요. 또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.

다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.

### <a name="projectreference"></a>ProjectReference

`ProjectReference` 항목은 다른 프로젝트에 대한 참조를 정의합니다. 참조된 프로젝트는 NuGet 패키지 종속성으로 추가됩니다. 즉, `PackageReference`와 동일하게 처리됩니다.

`Include` 특성은 프로젝트의 경로를 지정합니다. 또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.

다음 예제의 프로젝트 파일 코드 조각은 `Project2`라는 프로젝트를 참조합니다.

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a>참고

`Reference` 항목은 어셈블리 파일에 대한 참조를 정의합니다.

`Include` 특성은 파일의 이름을 지정하고, `HintPath` 메타데이터는 어셈블리의 경로를 지정합니다.

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a>복원 관련 속성

참조된 패키지를 복원하면 패키지의 직접 종속성과 해당 종속성의 종속성이 모두 설치됩니다. `RestorePackagesPath` 및 `RestoreIgnoreFailedSources`와 같은 속성을 지정하여 패키지 복원을 사용자 지정할 수 있습니다. 이러한 속성 및 다른 속성에 대한 자세한 내용은 [복원 대상](/nuget/reference/msbuild-targets#restore-target)을 참조하세요.

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a>실행 속성

다음 속성은 [`dotnet run`](../tools/dotnet-run.md) 명령을 사용하여 앱을 시작하는 데 사용됩니다.

- [RunArguments](#runarguments)
- [RunWorkingDirectory](#runworkingdirectory)

### <a name="runarguments"></a>RunArguments

`RunArguments` 속성은 앱이 실행될 때 앱에 전달되는 인수를 정의합니다.

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> [`dotnet run`의 `--` 옵션](../tools/dotnet-run.md#options)을 사용하면 앱에 전달할 추가 인수를 지정할 수 있습니다.

### <a name="runworkingdirectory"></a>RunWorkingDirectory

`RunWorkingDirectory` 속성은 애플리케이션 프로세스를 시작할 작업 디렉터리를 정의합니다. 디렉터리를 지정하지 않으면 `OutDir`이 작업 디렉터리로 사용됩니다.

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties-and-items"></a>호스팅 속성 및 항목

- [EnableComHosting](#enablecomhosting)
- [EnableDynamicLoading](#enabledynamicloading)

### <a name="enablecomhosting"></a>EnableComHosting

`EnableComHosting` 속성은 어셈블리가 COM 서버를 제공함을 나타냅니다. `EnableComHosting`을 `true`로 설정하면 [EnableDynamicLoading](#enabledynamicloading)도 `true`입니다.

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

자세한 내용은 [COM에 .NET 구성 요소 공개](../native-interop/expose-components-to-com.md)를 참조하세요.

### <a name="enabledynamicloading"></a>EnableDynamicLoading

`EnableDynamicLoading` 속성은 어셈블리가 동적으로 로드된 구성 요소임을 나타냅니다. 구성 요소는 [네이티브 호스트에서 사용](../tutorials/netcore-hosting.md)할 수 있는 [COM 라이브러리](/windows/win32/com/the-component-object-model) 또는 비 COM 라이브러리일 수 있습니다. 이 속성을 `true`로 설정하면 다음과 같은 효과가 있습니다.

- *.runtimeconfig.json* 파일이 생성됩니다.
- [롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)가 `LatestMinor`로 설정됩니다.
- NuGet 참조가 로컬로 복사됩니다.

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a>참조

- [MSBuild 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)
- [NuGet 압축의 MSBuild 속성](/nuget/reference/msbuild-targets#pack-target)
- [NuGet 복원의 MSBuild 속성](/nuget/reference/msbuild-targets#restore-properties)
- [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)
