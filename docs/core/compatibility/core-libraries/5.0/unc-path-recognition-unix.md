---
title: '호환성이 손상되는 변경: Unix에서 UNC 경로의 URI 인식'
description: Uri 클래스가 두 개의 슬래시로 시작하는 문자열을 Unix의 UNC 경로로 인식하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 65baaad5e1be7a8f61e3e62c976fd7e28f48730f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257026"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a>Unix에서 UNC 경로의 URI 인식

이제 <xref:System.Uri> 클래스가 두 개의 슬래시(`//`)로 시작하는 문자열을 Unix 운영 체제의 UNC(범용 명명 규칙) 경로로 인식합니다. 이 변경으로 인해 모든 플랫폼에서 해당 문자열에 대해 일관된 동작이 수행됩니다.

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET에서는 <xref:System.Uri> 클래스가 두 개의 슬래시로 시작하는 문자열(예: `//contoso`)을 Unix 운영 체제의 절대 파일 경로로 인식합니다. 그러나 Windows에서는 해당 문자열이 UNC 경로로 인식됩니다.

.NET 5부터 <xref:System.Uri> 클래스는 Unix를 비롯한 모든 플랫폼에서 두 개의 슬래시로 시작하는 문자열을 UNC 경로로 인식합니다. 또한 속성이 UNC 의미 체계에 따라 동작합니다.

- <xref:System.Uri.IsUnc?displayProperty=nameWithType>가 `true`를 반환하는 경우
- 경로의 백슬래시가 슬래시로 바뀝니다. 예를 들어 `//first\second`는 `//first/second`가 됩니다.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType>이 문자를 백분율 인코딩하지 않습니다. 예를 들어 `//first/\uFFF0`이 `//first/%EF%BF%B0`으로 변환되지 ‘않습니다’.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

개발자는 아무 작업도 수행하지 않아도 됩니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
