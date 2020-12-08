---
title: '호환성이 손상되는 변경: 지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ac7723cd9b961b34b3f87a55119d421668c87417
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437851"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="96041-103">지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨</span><span class="sxs-lookup"><span data-stu-id="96041-103">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="96041-104">[ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) 클래스 및 [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) 메서드가 .NET 5.0 미리 보기 1에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96041-104">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="96041-105">컨텍스트는 [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) 및 [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96041-105">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="96041-106">이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96041-106">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="96041-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="96041-107">Version introduced</span></span>

<span data-ttu-id="96041-108">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="96041-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="96041-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="96041-109">Old behavior</span></span>

<span data-ttu-id="96041-110">`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드는 [.NET Core 3.0 미리 보기 3 이상에서 사용되지 않습니다](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="96041-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="96041-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="96041-111">New behavior</span></span>

<span data-ttu-id="96041-112">`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드는 .NET 5.0 미리 보기 1에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96041-112">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="96041-113">변경된 내용의 인벤토리는 [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files)에서 끌어오기 요청을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96041-113">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="96041-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="96041-114">Reason for change</span></span>

<span data-ttu-id="96041-115">[ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) 클래스 및 [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) 메서드는 사용자가 지역화에 관해 혼란스러워하는 원인이기도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="96041-115">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="96041-116">특히 사용자 지정 <xref:Microsoft.Extensions.Localization.IStringLocalizer> 구현을 만들 때 크게 혼란스러워했습니다.</span><span class="sxs-lookup"><span data-stu-id="96041-116">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="96041-117">이 클래스와 메서드는 소비자가 `IStringLocalizer` 인스턴스가 “언어별, 리소스별”이어야 한다는 인상을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96041-117">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="96041-118">실제로 인스턴스는 “리소스별”이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96041-118">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="96041-119">런타임에 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> 속성은 사용할 언어를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="96041-119">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="96041-120">권장 조치</span><span class="sxs-lookup"><span data-stu-id="96041-120">Recommended action</span></span>

<span data-ttu-id="96041-121">`ResourceManagerWithCultureStringLocalizer` 클래스 및 `ResourceManagerStringLocalizer.WithCulture` 메서드 사용을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="96041-121">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="96041-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="96041-122">Affected APIs</span></span>

- [<span data-ttu-id="96041-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="96041-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="96041-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="96041-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
