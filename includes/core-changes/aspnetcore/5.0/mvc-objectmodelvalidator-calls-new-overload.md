---
ms.openlocfilehash: 5083403a24a4a695d6970ef9c7a006796f41a86b
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609302"
---
### <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="02186-101">MVC: ObjectModelValidator가 ValidationVisitor.Validate의 새 오버로드 호출</span><span class="sxs-lookup"><span data-stu-id="02186-101">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="02186-102">ASP.NET Core 5.0에서 <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>의 오버로드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02186-102">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="02186-103">새 오버로드는 다음 속성을 포함하는 최상위 수준 모델 인스턴스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="02186-103">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="02186-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator>는 `ValidationVisitor`의 새 오버로드를 호출하여 유효성 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="02186-104"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="02186-105">새 오버로드는 유효성 검사 라이브러리가 ASP.NET Core MVC의 모델 유효성 검사 시스템에 통합된 경우에만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02186-105">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="02186-106">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02186-106">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02186-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="02186-107">Version introduced</span></span>

<span data-ttu-id="02186-108">5.0</span><span class="sxs-lookup"><span data-stu-id="02186-108">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="02186-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="02186-109">Old behavior</span></span>

<span data-ttu-id="02186-110">`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02186-110">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

#### <a name="new-behavior"></a><span data-ttu-id="02186-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="02186-111">New behavior</span></span>

<span data-ttu-id="02186-112">`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02186-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

#### <a name="reason-for-change"></a><span data-ttu-id="02186-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="02186-113">Reason for change</span></span>

<span data-ttu-id="02186-114">이 변경 내용은 다른 속성 검사를 사용하는 <xref:System.ComponentModel.DataAnnotations.CompareAttribute>와 같은 유효성 검사기를 지원하기 위해 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02186-114">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02186-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="02186-115">Recommended action</span></span>

<span data-ttu-id="02186-116">.NET 5.0 이상을 대상으로 하는 경우 `ObjectModelValidator`를 사용하여 `ValidationVisitor`의 기존 오버로드를 호출하는 유효성 검사 프레임워크는 새 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02186-116">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

#### <a name="category"></a><span data-ttu-id="02186-117">범주</span><span class="sxs-lookup"><span data-stu-id="02186-117">Category</span></span>

<span data-ttu-id="02186-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02186-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02186-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="02186-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
