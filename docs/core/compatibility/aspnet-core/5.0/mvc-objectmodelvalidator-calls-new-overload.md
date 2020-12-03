---
title: '호환성이 손상되는 변경: MVC: ObjectModelValidator가 ValidationVisitor.Validate의 새 오버로드 호출'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. MVC: ObjectModelValidator가 ValidationVisitor.Validate의 새 오버로드 호출'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b28c357f51291a4f73889d5d413a983f79e09daf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760014"
---
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a><span data-ttu-id="24281-103">MVC: ObjectModelValidator가 ValidationVisitor.Validate의 새 오버로드 호출</span><span class="sxs-lookup"><span data-stu-id="24281-103">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>

<span data-ttu-id="24281-104">ASP.NET Core 5.0에서 <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>의 오버로드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24281-104">In ASP.NET Core 5.0, an overload of the <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType> was added.</span></span> <span data-ttu-id="24281-105">새 오버로드는 다음 속성을 포함하는 최상위 수준 모델 인스턴스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-105">The new overload accepts the top-level model instance that contains properties:</span></span>

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<span data-ttu-id="24281-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator>는 `ValidationVisitor`의 새 오버로드를 호출하여 유효성 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-106"><xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator> invokes this new overload of `ValidationVisitor` to perform validation.</span></span> <span data-ttu-id="24281-107">새 오버로드는 유효성 검사 라이브러리가 ASP.NET Core MVC의 모델 유효성 검사 시스템에 통합된 경우에만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24281-107">This new overload is pertinent if your validation library integrates with ASP.NET Core MVC's model validation system.</span></span>

<span data-ttu-id="24281-108">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24281-108">For discussion, see GitHub issue [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="24281-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="24281-109">Version introduced</span></span>

<span data-ttu-id="24281-110">5.0</span><span class="sxs-lookup"><span data-stu-id="24281-110">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="24281-111">이전 동작</span><span class="sxs-lookup"><span data-stu-id="24281-111">Old behavior</span></span>

<span data-ttu-id="24281-112">`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-112">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a><span data-ttu-id="24281-113">새 동작</span><span class="sxs-lookup"><span data-stu-id="24281-113">New behavior</span></span>

<span data-ttu-id="24281-114">`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-114">`ObjectModelValidator` invokes the following overload during model validation:</span></span>

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a><span data-ttu-id="24281-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="24281-115">Reason for change</span></span>

<span data-ttu-id="24281-116">이 변경 내용은 다른 속성 검사를 사용하는 <xref:System.ComponentModel.DataAnnotations.CompareAttribute>와 같은 유효성 검사기를 지원하기 위해 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24281-116">This change was introduced to support validators, such as <xref:System.ComponentModel.DataAnnotations.CompareAttribute>, that rely on inspection of other properties.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="24281-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="24281-117">Recommended action</span></span>

<span data-ttu-id="24281-118">.NET 5.0 이상을 대상으로 하는 경우 `ObjectModelValidator`를 사용하여 `ValidationVisitor`의 기존 오버로드를 호출하는 유효성 검사 프레임워크는 새 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-118">Validation frameworks that rely on `ObjectModelValidator` to invoke the existing overload of `ValidationVisitor` must override the new method when targeting .NET 5.0 or later:</span></span>

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a><span data-ttu-id="24281-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="24281-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
