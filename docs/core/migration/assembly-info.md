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
# <a name="map-assemblyinfo-attributes-to-properties"></a><span data-ttu-id="1c945-103">속성에 AssemblyInfo 특성 매핑</span><span class="sxs-lookup"><span data-stu-id="1c945-103">Map AssemblyInfo attributes to properties</span></span>

<span data-ttu-id="1c945-104">일반적으로 .NET Core 2.0의 *AssemblyInfo* 파일에 존재했던 [어셈블리 특성](../../standard/assembly/set-attributes.md)은 .NET Core 2.1부터 MSBuild 속성에서 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-104">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file in .NET Core 2.0 and earlier versions are automatically generated from MSBuild properties, starting in .NET Core 2.1.</span></span>

## <a name="properties-per-attribute"></a><span data-ttu-id="1c945-105">특성별 속성</span><span class="sxs-lookup"><span data-stu-id="1c945-105">Properties per attribute</span></span>

<span data-ttu-id="1c945-106">다음 표에 나온 것처럼 각 특성에는 해당 콘텐츠를 제어하는 일치하는 속성과 생성을 사용하지 않도록 설정하는 또 다른 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-106">As shown in the following table, each attribute has a corresponding property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="1c945-107">특성</span><span class="sxs-lookup"><span data-stu-id="1c945-107">Attribute</span></span>                                                      | <span data-ttu-id="1c945-108">속성</span><span class="sxs-lookup"><span data-stu-id="1c945-108">Property</span></span>               | <span data-ttu-id="1c945-109">사용하지 않도록 설정할 속성</span><span class="sxs-lookup"><span data-stu-id="1c945-109">Property to disable</span></span>                             |
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

<span data-ttu-id="1c945-110">메모:</span><span class="sxs-lookup"><span data-stu-id="1c945-110">Notes:</span></span>

- <span data-ttu-id="1c945-111">`AssemblyVersion` 및 `FileVersion`은 기본적으로 접미사가 없는 `$(Version)` 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-111">`AssemblyVersion` and `FileVersion` default to the value of `$(Version)` without the suffix.</span></span> <span data-ttu-id="1c945-112">예를 들어 `$(Version)`가 `1.2.3-beta.4`인 경우 값은 `1.2.3`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-112">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="1c945-113">`InformationalVersion`은 기본적으로 `$(Version)` 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-113">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="1c945-114">`$(SourceRevisionId)` 속성이 있는 경우 `InformationalVersion`에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-114">If the `$(SourceRevisionId)` property is present, it's appended to `InformationalVersion`.</span></span> <span data-ttu-id="1c945-115">해당 동작은 `IncludeSourceRevisionInInformationalVersion`을 사용하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-115">You can disable this behavior using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="1c945-116">`Copyright` 및 `Description` 속성도 NuGet 메타데이터에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-116">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="1c945-117">기본값이 `Debug`인 `Configuration`은 모든 MSBuild 대상과 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-117">`Configuration`, which defaults to `Debug`, is shared with all MSBuild targets.</span></span> <span data-ttu-id="1c945-118">`dotnet` 명령의 `--configuration` 옵션(예: [dotnet pack](../tools/dotnet-pack.md))을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-118">You can set it via the `--configuration` option of `dotnet` commands, for example, [dotnet pack](../tools/dotnet-pack.md).</span></span>

## <a name="generateassemblyinfo"></a><span data-ttu-id="1c945-119">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="1c945-119">GenerateAssemblyInfo</span></span>

<span data-ttu-id="1c945-120">모든 AssemblyInfo 생성을 사용하거나 사용하지 않도록 설정하는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-120">A Boolean that enables or disables the AssemblyInfo generation.</span></span> <span data-ttu-id="1c945-121">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-121">The default value is `true`.</span></span>

## <a name="generatedassemblyinfofile"></a><span data-ttu-id="1c945-122">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="1c945-122">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="1c945-123">생성된 어셈블리 정보 파일의 상대 또는 절대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-123">The relative or absolute path of the generated assembly info file.</span></span> <span data-ttu-id="1c945-124">기본값은 `$(IntermediateOutputPath)`(*obj*) 디렉터리에 있는 *[project-name].AssemblyInfo.[cs|vb]* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1c945-124">Defaults to a file named *[project-name].AssemblyInfo.[cs|vb]* in the `$(IntermediateOutputPath)` (*obj*) directory.</span></span>
