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
# <a name="mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate"></a>MVC: ObjectModelValidator가 ValidationVisitor.Validate의 새 오버로드 호출

ASP.NET Core 5.0에서 <xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>의 오버로드가 추가되었습니다. 새 오버로드는 다음 속성을 포함하는 최상위 수준 모델 인스턴스를 적용합니다.

```diff
  bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel);
+ bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container);
```

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.ObjectModelValidator>는 `ValidationVisitor`의 새 오버로드를 호출하여 유효성 검사를 수행합니다. 새 오버로드는 유효성 검사 라이브러리가 ASP.NET Core MVC의 모델 유효성 검사 시스템에 통합된 경우에만 관련이 있습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#26020](https://github.com/dotnet/aspnetcore/issues/26020)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="old-behavior"></a>이전 동작

`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel)
```

## <a name="new-behavior"></a>새 동작

`ObjectModelValidator`가 모델 유효성 검사 중에 다음 오버로드를 호출합니다.

```csharp
ValidationVisitor.Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
```

## <a name="reason-for-change"></a>변경 이유

이 변경 내용은 다른 속성 검사를 사용하는 <xref:System.ComponentModel.DataAnnotations.CompareAttribute>와 같은 유효성 검사기를 지원하기 위해 도입되었습니다.

## <a name="recommended-action"></a>권장 조치

.NET 5.0 이상을 대상으로 하는 경우 `ObjectModelValidator`를 사용하여 `ValidationVisitor`의 기존 오버로드를 호출하는 유효성 검사 프레임워크는 새 메서드를 재정의해야 합니다.

```csharp
public class MyCustomValidationVisitor : ValidationVisitor
{
+  public override bool Validate(ModelMetadata metadata, string key, object model, bool alwaysValidateAtTopLevel, object container)
+  {
+    ...
}
```

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.Validate`

-->
