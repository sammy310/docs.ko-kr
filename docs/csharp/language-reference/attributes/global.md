---
title: 'C# 예약된 특성: 전역 특성'
ms.date: 04/09/2020
description: 특성은 컴파일러가 프로그램의 더 많은 의미 체계를 이해하는 데 사용하는 메타데이터를 제공합니다.
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389807"
---
# <a name="reserved-attributes-assembly-level-attributes"></a><span data-ttu-id="e9aa1-103">예약된 특성: 어셈블리 수준 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-103">Reserved attributes: Assembly level attributes</span></span>

<span data-ttu-id="e9aa1-104">대부분의 특성은 클래스나 메서드와 같은 특정 언어 요소에 적용되지만 일부 특성은 전체 어셈블리나 모듈에 적용되는 전역 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-104">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="e9aa1-105">예를 들어 다음과 같이 <xref:System.Reflection.AssemblyVersionAttribute> 특성을 사용하여 버전 정보를 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-105">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

<span data-ttu-id="e9aa1-106">전역 특성은 소스 코드에서 최상위 `using` 지시문 뒤 그리고 형식, 모듈 또는 네임스페이스 선언 앞에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-106">Global attributes appear in the source code after any top level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="e9aa1-107">전역 특성은 여러 소스 파일에 나타날 수 있지만 파일은 하나의 컴파일 패스에서 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-107">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="e9aa1-108">Visual Studio는 .NET Framework 프로젝트의 AssemblyInfo.cs 파일에 전역 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-108">Visual Studio adds global attributes to the AssemblyInfo.cs file in .NET Framework projects.</span></span> <span data-ttu-id="e9aa1-109">해당 특성은 .NET Core 프로젝트에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-109">These attributes aren't added to .NET Core projects.</span></span>

<span data-ttu-id="e9aa1-110">어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-110">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="e9aa1-111">어셈블리 특성은 다음 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-111">They fall into the following categories:</span></span>

- <span data-ttu-id="e9aa1-112">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-112">Assembly identity attributes</span></span>
- <span data-ttu-id="e9aa1-113">정보 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-113">Informational attributes</span></span>
- <span data-ttu-id="e9aa1-114">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-114">Assembly manifest attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="e9aa1-115">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-115">Assembly identity attributes</span></span>

<span data-ttu-id="e9aa1-116">name, version 및 culture의 세 가지 특성(해당하는 경우 강력한 이름 포함)이 어셈블리의 ID를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-116">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="e9aa1-117">이러한 특성은 어셈블리의 전체 이름을 구성하며 코드에서 어셈블리를 참조할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-117">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="e9aa1-118">특성을 사용하여 어셈블리의 버전 및 문화권을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-118">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="e9aa1-119">그러나 이름 값은 어셈블리가 만들어질 때 컴파일러, [어셈블리 정보 대화 상자](/visualstudio/ide/reference/assembly-information-dialog-box)의 Visual Studio IDE 또는 어셈블리 링커(Al.exe)에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-119">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created.</span></span> <span data-ttu-id="e9aa1-120">어셈블리 이름은 어셈블리 매니페스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-120">The assembly name is based on the assembly manifest.</span></span> <span data-ttu-id="e9aa1-121"><xref:System.Reflection.AssemblyFlagsAttribute> 특성은 어셈블리의 여러 복사본이 공존할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-121">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="e9aa1-122">다음 표에서는 ID 특성들을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-122">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="e9aa1-123">특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-123">Attribute</span></span>|<span data-ttu-id="e9aa1-124">용도</span><span class="sxs-lookup"><span data-stu-id="e9aa1-124">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="e9aa1-125">어셈블리의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-125">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="e9aa1-126">어셈블리에서 지원하는 문화권을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-126">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="e9aa1-127">어셈블리가 같은 컴퓨터, 같은 프로세스 또는 같은 애플리케이션 도메인에서 Side-by-side 실행을 지원하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-127">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

## <a name="informational-attributes"></a><span data-ttu-id="e9aa1-128">정보 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-128">Informational attributes</span></span>

<span data-ttu-id="e9aa1-129">정보 특성을 사용하여 어셈블리와 연관된 회사 또는 제품에 대한 추가적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-129">You use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="e9aa1-130">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 정보 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-130">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="e9aa1-131">특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-131">Attribute</span></span>|<span data-ttu-id="e9aa1-132">용도</span><span class="sxs-lookup"><span data-stu-id="e9aa1-132">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="e9aa1-133">어셈블리 매니페스트의 제품 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-133">Specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="e9aa1-134">어셈블리 매니페스트의 상표를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-134">Specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="e9aa1-135">어셈블리 매니페스트의 정보 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-135">Specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="e9aa1-136">어셈블리 매니페스트의 회사 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-136">Specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="e9aa1-137">어셈블리 매니페스트에 대한 저작권을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-137">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="e9aa1-138">Win32 파일 버전 리소스의 특정 버전 번호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-138">Sets a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="e9aa1-139">어셈블리가 CLS(공용 언어 사양)을 준수하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-139">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="e9aa1-140">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-140">Assembly manifest attributes</span></span>

<span data-ttu-id="e9aa1-141">어셈블리 매니페스트 특성을 사용하여 어셈블리 매니페스트의 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-141">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="e9aa1-142">특성에는 제목, 설명, 기본 별칭 및 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-142">The attributes include title, description, default alias, and configuration.</span></span> <span data-ttu-id="e9aa1-143">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 어셈블리 매니페스트 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-143">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="e9aa1-144">특성</span><span class="sxs-lookup"><span data-stu-id="e9aa1-144">Attribute</span></span>|<span data-ttu-id="e9aa1-145">용도</span><span class="sxs-lookup"><span data-stu-id="e9aa1-145">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="e9aa1-146">어셈블리 매니페스트의 어셈블리 제목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-146">Specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="e9aa1-147">어셈블리 매니페스트의 어셈블리 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-147">Specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="e9aa1-148">어셈블리 매니페스트의 어셈블리 구성(예: 정품 또는 디버그)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-148">Specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="e9aa1-149">어셈블리 매니페스트에 대한 친숙한 기본 별칭을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa1-149">Defines a friendly default alias for an assembly manifest</span></span>|
