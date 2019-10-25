---
ms.openlocfilehash: dc9f37ae0cd6eef2c67e62421571290bba1c2233
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394385"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC: 컨트롤러 작업 이름에서 잘린 비동기 접미사

[aspnet/AspNetCore#4849](https://github.com/aspnet/AspNetCore/issues/4849)를 해결하는 과정의 일부로, ASP.NET Core MVC는 기본적으로 작업 이름에서 `Async` 접미사를 잘라냅니다. ASP.NET Core 3.0부터 이 변경 내용은 라우팅 및 링크 생성 모두에 영향을 줍니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

다음 ASP.NET Core MVC 컨트롤러를 고려하세요.

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

작업은 `Product/ListAsync`를 통해 라우팅할 수 있습니다. 링크 생성을 위해서는 `Async` 접미사를 지정해야 합니다. 예:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>새 동작

ASP.NET Core 3.0에서 작업은 `Product/List`를 통해 라우팅할 수 있습니다. 링크 생성 코드는 `Async` 접미사를 생략해야 합니다. 예:

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

이 변경 내용은 `[ActionName]` 특성을 사용하여 지정된 이름에는 영향을 주지 않습니다. `Startup.ConfigureServices`에서 `MvcOptions.SuppressAsyncSuffixInActionNames`를 `false`로 설정하여 새 동작을 사용하지 않도록 설정할 수 있습니다.

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false; 
});
```

#### <a name="reason-for-change"></a>변경 이유

규칙에 따라 비동기 .NET 메서드는 `Async`로 접미사가 붙습니다. 그러나 메서드가 MVC 작업을 정의할 때 `Async` 접미사를 사용하는 것은 바람직하지 않습니다.

#### <a name="recommended-action"></a>권장 작업

앱이 이름의 `Async` 접미사를 유지하는 MVC 작업에 의존하는 경우 다음 완화 방법 중 하나를 선택합니다.

- `[ActionName]` 특성을 사용하여 원래 이름을 유지합니다.
- `Startup.ConfigureServices`에서 `MvcOptions.SuppressAsyncSuffixInActionNames`를 `false`로 설정하여 전체 이름 바꾸기를 사용하지 않도록 설정합니다.

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false; 
});
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
