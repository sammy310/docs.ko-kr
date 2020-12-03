---
title: '호환성이 손상되는 변경: IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759600"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨

IIS UrlRewrite 미들웨어 결함으로 인해 쿼리 문자열이 다시 쓰기 규칙에서 유지되지 않았습니다. IIS UrlRewrite 모듈 동작과 일관성을 유지하기 위해 해당 결함이 수정되었습니다.

자세한 내용은 이슈 [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

ASP.NET Core 5.0 미리 보기 7

## <a name="old-behavior"></a>이전 동작

다음 다시 작성 규칙을 살펴보세요.

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

위의 규칙에서는 쿼리 문자열을 추가하지 않습니다. `/about?id=1`과 같은 URI는 `/contact?id=1`이 아니라 `/contact`로 리디렉션됩니다. `appendQueryString` 특성의 기본값도 `true`로 설정됩니다.

## <a name="new-behavior"></a>새 동작

쿼리 문자열이 유지됩니다. [이전 동작](#old-behavior)의 예제에서 URI가 `/contact?id=1`이 됩니다.

## <a name="reason-for-change"></a>변경 이유

이전 동작은 IIS UrlRewrite 모듈의 동작과 일치하지 않았습니다. 미들웨어와 모듈 간의 이식을 지원하기 위해서는 일관된 동작을 유지해야 합니다.

## <a name="recommended-action"></a>권장 조치

쿼리 문자열을 제거하는 동작을 원하는 경우 `action` 요소를 `appendQueryString="false"`로 설정합니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
