---
title: MSBuild에서 매니페스트 파일 이름을 생성하는 방법
description: 컴파일 시간에 MSBuild에서 생성되는 리소스 매니페스트 파일 이름에 영향을 주는 요소를 설명합니다.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 2e0461e34bbd7f8da35bea1db1913a32915c7117
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970683"
---
# <a name="how-resource-manifest-files-are-named"></a>리소스 매니페스트 파일의 이름을 지정하는 방법

MSBuild에서 .NET Core 프로젝트를 컴파일할 때 파일 확장명이 *.resx* 인 XML 리소스 파일이 이진 *.resources* 파일로 변환됩니다. 해당 이진 파일은 컴파일러의 출력에 포함되며 <xref:System.Resources.ResourceManager>에서 읽을 수 있습니다. 이 문서에서는 MSBuild에서 각 *.resources* 파일의 이름을 선택하는 방법을 설명합니다.

> [!TIP]
> 프로젝트 파일에 리소스 항목을 명시적으로 추가하고 해당 항목이 [.NET Core용 기본 포함 GLOB에도 포함](../project-sdk/overview.md#default-includes-and-excludes)되는 경우 빌드 오류가 발생합니다. 수동으로 리소스 파일을 `EmbeddedResource` 항목으로 포함하려면 `EnableDefaultEmbeddedResourceItems` 속성을 false로 설정합니다.

## <a name="default-name"></a>기본 이름

.NET Core 3.0 이상에서는 다음 조건을 모두 충족하는 경우 리소스 매니페스트의 기본 이름이 사용됩니다.

- 리소스 파일이 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터를 사용하여 `EmbeddedResource` 항목으로 프로젝트 파일에 명시적으로 포함되어 있지 않습니다.
- 프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention` 속성이 `false`로 설정되어 있지 않습니다. 기본적으로 이 속성은 `true`로 설정됩니다. 자세한 내용은 [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention)을 참조하세요.

리소스 파일이 동일한 루트 파일 이름의 소스 파일( *.cs* 또는 *.vb*)과 함께 배치된 경우 소스 파일에 정의된 첫 번째 형식의 전체 이름이 매니페스트 파일 이름으로 사용됩니다. 예를 들어 `MyNamespace.Form1`이 *Form1.cs* 에 정의된 첫 번째 형식이고 *Form1.cs* 가 *Form1.resx* 와 함께 배치된 경우 해당 리소스 파일의 생성된 매니페스트 이름은 *MyNamespace.Form1.resources* 입니다.

## <a name="logicalname-metadata"></a>LogicalName 메타데이터

리소스 파일이 프로젝트 파일에 `LogicalName` 메타데이터를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `LogicalName` 값이 매니페스트 이름으로 사용됩니다. `LogicalName`이 다른 메타데이터나 설정보다 우선 적용됩니다.

예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.resources* 입니다.

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

또는

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a>ManifestResourceName 메타데이터

리소스 파일이 프로젝트 파일에 `ManifestResourceName` 메타데이터(`LogicalName`은 없음)를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `ManifestResourceName` 값이 파일 확장명 *.resources* 와 함께 매니페스트 파일 이름으로 사용됩니다.

예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.resources* 입니다.

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

다음 프로젝트 파일 코드 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.fr-FR.resources* 입니다.

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a>DependentUpon 메타데이터

리소스 파일이 프로젝트 파일에 `DependentUpon` 메타데이터(`LogicalName` 및 `ManifestResourceName`은 없음)를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `DependentUpon`에 정의된 소스 파일의 정보가 리소스 매니페스트 파일 이름에 사용됩니다. 특히 소스 파일에 정의된 첫 번째 형식의 이름이 다음과 같이 매니페스트 이름에 사용됩니다. *Namespace.Classname\[.Culture].resources*.

예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *Namespace.Classname.resources* 입니다. 여기서 `Namespace.Classname`은 *MyTypes.cs* 에 정의된 첫 번째 클래스입니다.

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 입니다. 여기서 `Namespace.Classname`은 *MyTypes.cs* 에 정의된 첫 번째 클래스입니다.

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a>EmbeddedResourceUseDependentUponConvention 속성

프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`이 `false`로 설정된 경우 각 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 프로젝트 루트에서 *.resx* 파일까지의 상대 경로를 기반으로 합니다. 더 구체적으로 생성된 리소스 매니페스트 파일 이름은 *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources* 입니다. 같은 논리가 3.0 이전 버전의 .NET Core에서 매니페스트 이름을 생성하는 데에도 사용됩니다.

> [!NOTE]
>
> - `RootNamespace`은 정의되지 않은 경우 기본적으로 프로젝트 이름으로 설정됩니다.
> - 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정된 경우 해당 리소스 파일에는 이 명명 규칙이 적용되지 않습니다.

## <a name="see-also"></a>참조

- [매니페스트 리소스 명명 방식](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [.NET Core SDK 프로젝트의 MSBuild 속성](../project-sdk/msbuild-props.md)
- [MSBuild 호환성이 손상되는 변경 사항](../compatibility/msbuild.md)
