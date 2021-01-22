---
title: AssemblyInfo 속성
description: 어셈블리 특성 및 해당 특성을 .NET Core 2.1 이상 버전의 MSBuild 속성에 일치시키는 방법에 관해 알아봅니다.
ms.topic: reference
ms.date: 01/08/2021
ms.openlocfilehash: a2c431b3fe3da428f21582624ca5f357887e2815
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98192877"
---
# <a name="map-assemblyinfo-attributes-to-properties"></a>속성에 AssemblyInfo 특성 매핑

일반적으로 .NET Core 2.0의 *AssemblyInfo* 파일에 존재했던 [어셈블리 특성](../../standard/assembly/set-attributes.md)은 .NET Core 2.1부터 MSBuild 속성에서 자동으로 생성됩니다.

## <a name="properties-per-attribute"></a>특성별 속성

다음 표에 나온 것처럼 각 특성에는 해당 콘텐츠를 제어하는 일치하는 속성과 생성을 사용하지 않도록 설정하는 또 다른 속성이 있습니다.

| 특성                                                      | 속성               | 사용하지 않도록 설정할 속성                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

메모:

- `AssemblyVersion` 및 `FileVersion`은 기본적으로 접미사가 없는 `$(Version)` 값으로 설정됩니다. 예를 들어 `$(Version)`가 `1.2.3-beta.4`인 경우 값은 `1.2.3`입니다.
- `InformationalVersion`은 기본적으로 `$(Version)` 값으로 설정됩니다.
- `$(SourceRevisionId)` 속성이 있는 경우 `InformationalVersion`에 추가됩니다. 해당 동작은 `IncludeSourceRevisionInInformationalVersion`을 사용하여 사용하지 않도록 설정할 수 있습니다.
- `Copyright` 및 `Description` 속성도 NuGet 메타데이터에 사용됩니다.
- 기본값이 `Debug`인 `Configuration`은 모든 MSBuild 대상과 공유합니다. `dotnet` 명령의 `--configuration` 옵션(예: [dotnet pack](../tools/dotnet-pack.md))을 통해 설정할 수 있습니다.

## <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

모든 AssemblyInfo 생성을 사용하거나 사용하지 않도록 설정하는 부울입니다. 기본값은 `true`입니다.

## <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

생성된 어셈블리 정보 파일의 상대 또는 절대 경로입니다. 기본값은 `$(IntermediateOutputPath)`(*obj*) 디렉터리에 있는 *[project-name].AssemblyInfo.[cs|vb]* 파일입니다.
