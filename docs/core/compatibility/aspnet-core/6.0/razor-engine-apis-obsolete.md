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
# <a name="razor-razorengine-apis-marked-obsolete"></a>Razor: RazorEngine API가 사용되지 않음으로 표시됨

Blazor의 <xref:Microsoft.AspNetCore.Razor.Language.RazorEngine> 형식과 관련된 형식이 사용되지 않음으로 표시되었습니다.

## <a name="version-introduced"></a>도입된 버전

6.0 미리 보기 1

## <a name="old-behavior"></a>이전 동작

`RazorEngine` API는 사용되지 않습니다.

## <a name="new-behavior"></a>새 동작

`RazorEngine` API는 사용되지 않습니다.

## <a name="reason-for-change"></a>변경 이유

`RazorEngine` 형식은 사용되지 않으며 대신 <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine> 형식이 사용됩니다.

## <a name="recommended-action"></a>권장 조치

`RazorEngine` 형식에서 `RazorProjectEngine` 형식으로 소스 코드를 마이그레이션합니다.

## <a name="affected-apis"></a>영향을 받는 API

- [Microsoft.AspNetCore.Mvc.Razor.Extensions.InjectDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.injectdirective.register?view=aspnetcore-3.1&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.ModelDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Mvc.Razor.Extensions.PageDirective.Register](/dotnet/api/microsoft.aspnetcore.mvc.razor.extensions.namespacedirective.register?view=aspnetcore-2.2&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.FunctionsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.functionsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.InheritsDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.inheritsdirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.Extensions.SectionDirective.Register](/dotnet/api/microsoft.aspnetcore.razor.language.extensions.sectiondirective.register?view=aspnetcore-3.0&preserve-view=true)
- [Microsoft.AspNetCore.Razor.Language.IRazorEngineBuilder](/dotnet/api/microsoft.aspnetcore.razor.language.irazorenginebuilder?view=aspnetcore-3.0&preserve-view=true)

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
