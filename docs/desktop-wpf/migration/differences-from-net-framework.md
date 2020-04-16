---
title: .NET 프레임워크와 .NET 코어의 차이점
description: WPF(Windows 프레젠테이션 파운데이션)의 .NET 프레임워크 구현과 .NET 코어 WPF 간의 차이점에 대해 설명합니다. 앱을 마이그레이션할 때 이러한 비호환성을 고려해야 합니다.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433135"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="d203d-104">WPF의 차이</span><span class="sxs-lookup"><span data-stu-id="d203d-104">Differences in WPF</span></span>

<span data-ttu-id="d203d-105">이 문서에서는 .NET 코어와 .NET 프레임워크에서 WPF(Windows 프레젠테이션 파운데이션)의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="d203d-106">.NET 코어용 WPF는 .NET Framework 소스 코드에 대한 원래 WPF에서 포크된 [오픈 소스](https://github.com/dotnet/wpf) 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="d203d-107">.NET Core에서 지원하지 않는 몇 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="d203d-108">지원되지 않는 기술에 대한 자세한 내용은 [.NET Core에서 사용할 수 없는 .NET Framework 기술을](../../core/porting/net-framework-tech-unavailable.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d203d-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="d203d-109">SDK 스타일 프로젝트</span><span class="sxs-lookup"><span data-stu-id="d203d-109">SDK-style projects</span></span>

<span data-ttu-id="d203d-110">.NET Core는 SDK 스타일 프로젝트 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="d203d-111">이러한 프로젝트 파일은 Visual Studio에서 관리하는 기존 .NET Framework 프로젝트 파일과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="d203d-112">.NET 프레임워크 WPF 앱을 .NET Core로 마이그레이션하려면 프로젝트를 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="d203d-113">자세한 내용은 [WPF 앱을 .NET Core 3.0으로 마이그레이션을](convert-project-from-net-framework.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d203d-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="d203d-114">NuGet 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="d203d-114">NuGet package references</span></span>

<span data-ttu-id="d203d-115">.NET Framework 앱이 *packages.config* 파일에 NuGet 종속성을 나열하는 경우 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 다음 형식으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="d203d-116">시각적 스튜디오에서 솔루션 **탐색기** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="d203d-117">WPF 프로젝트에서 패키지 를 마우스 오른쪽 단추로 **클릭합니다.config** > **는 packageReference.**</span><span class="sxs-lookup"><span data-stu-id="d203d-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![패키지참조로 업그레이드](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="d203d-119">계산된 최상위 NuGet 종속성을 표시하고 상위 수준으로 승격해야 하는 다른 NuGet 패키지를 묻는 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="d203d-120">**확인을** 선택하면 *packages.config* 파일이 프로젝트에서 제거되고 `<PackageReference>` 요소가 프로젝트 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="d203d-121">프로젝트에서 를 `<PackageReference>`사용하면 패키지가 *패키지* 폴더에 로컬로 저장되지 않고 전역적으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="d203d-122">프로젝트 파일을 열고 패키지 `<Analyzer>` 폴더를 참조하는 요소를 *제거합니다.*</span><span class="sxs-lookup"><span data-stu-id="d203d-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="d203d-123">이러한 분석기는 NuGet 패키지 참조에 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="d203d-124">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="d203d-124">Code Access Security</span></span>

<span data-ttu-id="d203d-125">CAS(코드 액세스 보안)는 .NET 코어 또는 .NET 코어에 대한 WPF에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="d203d-126">모든 CAS 관련 기능은 완전 신뢰의 가정하에 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="d203d-127">.NET 코어용 WPF는 CAS 관련 코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="d203d-128">이러한 형식에 대한 호출이 성공할 수 있도록 이러한 형식의 공용 API 표시면이 여전히 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="d203d-129">공개적으로 정의된 CAS 관련 형식은 WPF 어셈블리에서 CoreFX 어셈블리로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the CoreFX assemblies.</span></span> <span data-ttu-id="d203d-130">WPF 어셈블리에는 이동된 형식의 새 위치로 형식 전달 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="d203d-131">소스 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d203d-131">Source assembly</span></span> | <span data-ttu-id="d203d-132">대상 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d203d-132">Target assembly</span></span> | <span data-ttu-id="d203d-133">Type</span><span class="sxs-lookup"><span data-stu-id="d203d-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="d203d-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="d203d-135">*시스템.보안.권한.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="d203d-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="d203d-137">*시스템.보안.권한.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="d203d-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="d203d-139">*시스템.윈도우.확장.dll*</span><span class="sxs-lookup"><span data-stu-id="d203d-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="d203d-140">포팅 마찰을 최소화하기 위해 다음 속성과 관련된 정보를 저장하고 검색하는 `XamlAccessLevel` 기능이 형식에 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="d203d-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d203d-141">Next steps</span></span>

- [<span data-ttu-id="d203d-142">.NET 프레임워크 WPF 앱을 .NET Core로 포팅하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d203d-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
