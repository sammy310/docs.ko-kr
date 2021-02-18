---
title: '호환성이 손상되는 변경: Razor: RazorEngine API가 사용되지 않음으로 표시됨'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 관해 알아보기. Razor: RazorEngine API가 사용되지 않음으로 표시됨'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: 173ff0ee5c062f050c967c6edc7bed333d1a2031
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488229"
---
# <a name="razor-razorengine-apis-marked-obsolete"></a><span data-ttu-id="b795a-103">Razor: RazorEngine API가 사용되지 않음으로 표시됨</span><span class="sxs-lookup"><span data-stu-id="b795a-103">Razor: RazorEngine APIs marked obsolete</span></span>

<span data-ttu-id="b795a-104">Blazor의 <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> 형식과 관련된 형식이 사용되지 않음으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b795a-104">Types related to the <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> type in Blazor have been marked as obsolete.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b795a-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b795a-105">Version introduced</span></span>

<span data-ttu-id="b795a-106">6.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="b795a-106">6.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b795a-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="b795a-107">Old behavior</span></span>

<span data-ttu-id="b795a-108">`RazorEngine` API는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b795a-108">The `RazorEngine` APIs aren't obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="b795a-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="b795a-109">New behavior</span></span>

<span data-ttu-id="b795a-110">`RazorEngine` API는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b795a-110">The `RazorEngine` APIs are obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b795a-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b795a-111">Reason for change</span></span>

<span data-ttu-id="b795a-112">`RazorEngine` 형식은 사용되지 않으며 대신 <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b795a-112">The `RazorEngine` type has been deprecated in favor of the <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> type.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b795a-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b795a-113">Recommended action</span></span>

<span data-ttu-id="b795a-114">`RazorEngine` 형식에서 `RazorProjectEngine` 형식으로 소스 코드를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="b795a-114">Migrate source code from the `RazorEngine` type to the `RazorProjectEngine` type.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b795a-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b795a-115">Affected APIs</span></span>

- [<span data-ttu-id="b795a-116">Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-116">Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.injectdirective.register?view=aspnetcore-3.1&preserve-view=true)
- [<span data-ttu-id="b795a-117">Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-117">Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [<span data-ttu-id="b795a-118">Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-118">Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [<span data-ttu-id="b795a-119">Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-119">Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.functionsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="b795a-120">Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-120">Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.inheritsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="b795a-121">Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register</span><span class="sxs-lookup"><span data-stu-id="b795a-121">Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.sectiondirective.register?view=aspnetcore-3.0&preserve-view=true)
- [<span data-ttu-id="b795a-122">Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder</span><span class="sxs-lookup"><span data-stu-id="b795a-122">Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.irazorenginebuilder?view=aspnetcore-3.0&preserve-view=true)

<!--

## Category

ASP.NET Core

## Affected APIs

- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register`
- `Overload:Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register`
- `Overload:Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register`
- `T:Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder`

-->
