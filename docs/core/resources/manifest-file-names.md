---
title: MSBuild에서 매니페스트 파일 이름을 생성하는 방법
description: 컴파일 시간에 MSBuild에서 생성되는 리소스 매니페스트 파일 이름에 영향을 주는 요소를 설명합니다.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866386"
---
# <a name="how-resource-manifest-files-are-named"></a><span data-ttu-id="7befe-103">리소스 매니페스트 파일의 이름을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="7befe-103">How resource manifest files are named</span></span>

<span data-ttu-id="7befe-104">MSBuild에서 .NET Core 프로젝트를 컴파일할 때 파일 확장명이 *.resx* 인 XML 리소스 파일이 이진 *.resources* 파일로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-104">When MSBuild compiles a .NET Core project, XML resource files, which have the *.resx* file extension, are converted into binary *.resources* files.</span></span> <span data-ttu-id="7befe-105">해당 이진 파일은 컴파일러의 출력에 포함되며 <xref:System.Resources.ResourceManager>에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-105">The binary files are embedded into the output of the compiler and can be read by the <xref:System.Resources.ResourceManager>.</span></span> <span data-ttu-id="7befe-106">이 문서에서는 MSBuild에서 각 *.resources* 파일의 이름을 선택하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-106">This article describes how MSBuild chooses a name for each *.resources* file.</span></span>

> [!TIP]
> <span data-ttu-id="7befe-107">프로젝트 파일에 리소스 항목을 명시적으로 추가하고 해당 항목이 [.NET Core용 기본 포함 GLOB에도 포함](../project-sdk/overview.md#default-compilation-includes)되는 경우 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-107">If you explicitly add a resource item to your project file, and it's also [included with the default include globs for .NET Core](../project-sdk/overview.md#default-compilation-includes), you will get a build error.</span></span> <span data-ttu-id="7befe-108">수동으로 리소스 파일을 `EmbeddedResource` 항목으로 포함하려면 `EnableDefaultEmbeddedResourceItems` 속성을 false로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-108">To manually include resource files as `EmbeddedResource` items, set the `EnableDefaultEmbeddedResourceItems` property to false.</span></span>

## <a name="default-name"></a><span data-ttu-id="7befe-109">기본 이름</span><span class="sxs-lookup"><span data-stu-id="7befe-109">Default name</span></span>

<span data-ttu-id="7befe-110">.NET Core 3.0 이상에서는 다음 조건을 모두 충족하는 경우 리소스 매니페스트의 기본 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-110">In .NET Core 3.0 and later, the default name for a resource manifest is used when both of the following conditions are met:</span></span>

- <span data-ttu-id="7befe-111">리소스 파일이 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터를 사용하여 `EmbeddedResource` 항목으로 프로젝트 파일에 명시적으로 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-111">The resource file is not explicitly included in the project file as an `EmbeddedResource` item with `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata.</span></span>
- <span data-ttu-id="7befe-112">프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention` 속성이 `false`로 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-112">The `EmbeddedResourceUseDependentUponConvention` property is not set to `false` in the project file.</span></span> <span data-ttu-id="7befe-113">기본적으로 이 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-113">By default, this property is set to `true`.</span></span> <span data-ttu-id="7befe-114">자세한 내용은 [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7befe-114">For more information, see [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span></span>

<span data-ttu-id="7befe-115">리소스 파일이 동일한 루트 파일 이름의 소스 파일( *.cs* 또는 *.vb*)과 함께 배치된 경우 소스 파일에 정의된 첫 번째 형식의 전체 이름이 매니페스트 파일 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-115">If the resource file is colocated with a source file (*.cs* or *.vb*) of the same root file name, the full name of the first type that's defined in the source file is used for the manifest file name.</span></span> <span data-ttu-id="7befe-116">예를 들어 `MyNamespace.Form1`이 *Form1.cs* 에 정의된 첫 번째 형식이고 *Form1.cs* 가 *Form1.resx* 와 함께 배치된 경우 해당 리소스 파일의 생성된 매니페스트 이름은 *MyNamespace.Form1.resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-116">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, and *Form1.cs* is colocated with *Form1.resx*, the generated manifest name for that resource file is *MyNamespace.Form1.resources*.</span></span>

## <a name="logicalname-metadata"></a><span data-ttu-id="7befe-117">LogicalName 메타데이터</span><span class="sxs-lookup"><span data-stu-id="7befe-117">LogicalName metadata</span></span>

<span data-ttu-id="7befe-118">리소스 파일이 프로젝트 파일에 `LogicalName` 메타데이터를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `LogicalName` 값이 매니페스트 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-118">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `LogicalName` metadata, the `LogicalName` value is used as the manifest name.</span></span> <span data-ttu-id="7befe-119">`LogicalName`이 다른 메타데이터나 설정보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-119">`LogicalName` takes precedence over any other metadata or setting.</span></span>

<span data-ttu-id="7befe-120">예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-120">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

<span data-ttu-id="7befe-121">또는</span><span class="sxs-lookup"><span data-stu-id="7befe-121">-or-</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a><span data-ttu-id="7befe-122">ManifestResourceName 메타데이터</span><span class="sxs-lookup"><span data-stu-id="7befe-122">ManifestResourceName metadata</span></span>

<span data-ttu-id="7befe-123">리소스 파일이 프로젝트 파일에 `ManifestResourceName` 메타데이터(`LogicalName`은 없음)를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `ManifestResourceName` 값이 파일 확장명 *.resources* 와 함께 매니페스트 파일 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-123">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `ManifestResourceName` metadata (and `LogicalName` is absent), the `ManifestResourceName` value, combined with the file extension *.resources*, is used as the manifest file name.</span></span>

<span data-ttu-id="7befe-124">예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-124">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

<span data-ttu-id="7befe-125">다음 프로젝트 파일 코드 조각에 정의된 리소스 파일의 매니페스트 이름은 *SomeName.fr-FR.resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-125">The manifest name for the resource file that's defined in the following project file snippet is *SomeName.fr-FR.resources*.</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a><span data-ttu-id="7befe-126">DependentUpon 메타데이터</span><span class="sxs-lookup"><span data-stu-id="7befe-126">DependentUpon metadata</span></span>

<span data-ttu-id="7befe-127">리소스 파일이 프로젝트 파일에 `DependentUpon` 메타데이터(`LogicalName` 및 `ManifestResourceName`은 없음)를 사용하여 `EmbeddedResource` 항목으로 명시적으로 포함된 경우 `DependentUpon`에 정의된 소스 파일의 정보가 리소스 매니페스트 파일 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-127">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `DependentUpon` metadata (and `LogicalName` and `ManifestResourceName` are absent), information from the source file defined by `DependentUpon` is used for the resource manifest file name.</span></span> <span data-ttu-id="7befe-128">특히 소스 파일에 정의된 첫 번째 형식의 이름이 다음과 같이 매니페스트 이름에 사용됩니다. *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="7befe-128">Specifically, the name of the first type that's defined in the source file is used in the manifest name as follows: *Namespace.Classname\[.Culture].resources*.</span></span>

<span data-ttu-id="7befe-129">예를 들어 다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 *Namespace.Classname.resources* 입니다. 여기서 `Namespace.Classname`은 *MyTypes.cs* 에 정의된 첫 번째 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-129">For example, the manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

<span data-ttu-id="7befe-130">다음 프로젝트 파일 조각에 정의된 리소스 파일의 매니페스트 이름은 입니다. 여기서 `Namespace.Classname`은 *MyTypes.cs* 에 정의된 첫 번째 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-130">The manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a><span data-ttu-id="7befe-131">EmbeddedResourceUseDependentUponConvention 속성</span><span class="sxs-lookup"><span data-stu-id="7befe-131">EmbeddedResourceUseDependentUponConvention property</span></span>

<span data-ttu-id="7befe-132">프로젝트 파일에서 `EmbeddedResourceUseDependentUponConvention`이 `false`로 설정된 경우 각 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 프로젝트 루트에서 *.resx* 파일까지의 상대 경로를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-132">If `EmbeddedResourceUseDependentUponConvention` is set to `false` in the project file, each resource manifest file name is based off the root namespace for the project and the relative path from the project root to the *.resx* file.</span></span> <span data-ttu-id="7befe-133">더 구체적으로 생성된 리소스 매니페스트 파일 이름은 *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-133">More specifically, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="7befe-134">같은 논리가 3.0 이전 버전의 .NET Core에서 매니페스트 이름을 생성하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-134">This is also the logic used to generate manifest names in .NET Core versions prior to 3.0.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7befe-135">`RootNamespace`은 정의되지 않은 경우 기본적으로 프로젝트 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-135">If `RootNamespace` is not defined, it defaults to the project name.</span></span>
> - <span data-ttu-id="7befe-136">프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정된 경우 해당 리소스 파일에는 이 명명 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7befe-136">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item in the project file, this naming rule does not apply to that resource file.</span></span>

## <a name="see-also"></a><span data-ttu-id="7befe-137">참조</span><span class="sxs-lookup"><span data-stu-id="7befe-137">See also</span></span>

- [<span data-ttu-id="7befe-138">매니페스트 리소스 명명 방식</span><span class="sxs-lookup"><span data-stu-id="7befe-138">How Manifest Resource Naming Works</span></span>](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [<span data-ttu-id="7befe-139">.NET Core SDK 프로젝트의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="7befe-139">MSBuild properties for .NET Core SDK projects</span></span>](../project-sdk/msbuild-props.md)
- [<span data-ttu-id="7befe-140">MSBuild 호환성이 손상되는 변경 사항</span><span class="sxs-lookup"><span data-stu-id="7befe-140">MSBuild breaking changes</span></span>](../compatibility/msbuild.md)
