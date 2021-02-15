---
title: '호환성이 손상되는 변경: 일부 API가 ArgumentNullException을 throw함'
description: 일부 API가 인수의 유효성을 검사하고 이제 ArgumentNullException을 throw하는 .NET 6.0의 주요 변경 내용에 대해 알아봅니다.
ms.date: 01/29/2021
ms.openlocfilehash: f9d7dc8bb57ed8dc5b4ff41bda9b3bde7db7b880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804153"
---
# <a name="some-apis-throw-argumentnullexception"></a>일부 API가 ArgumentNullException을 throw함

이제 일부 API는 입력 매개 변수의 유효성을 검사하여 `null` 입력 인수를 사용하여 호출된 경우 <xref:System.ArgumentNullException>을 throw합니다(이전에는 <xref:System.NullReferenceException>을 throw함).

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 영향을 받는 API는 `null`인 인수를 사용하여 호출된 경우 <xref:System.NullReferenceException>을 throw합니다.

.NET 6.0부터 영향을 받는 API는 `null`인 인수를 사용하여 호출된 경우 <xref:System.ArgumentNullException>을 throw합니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.ArgumentNullException>을 throw하면 .NET 런타임 동작을 따릅니다. 예외를 발생시킨 인수를 명확하게 전달하여 더 나은 디버그 환경을 제공합니다.

## <a name="version-introduced"></a>도입된 버전

.NET 6.0

## <a name="recommended-action"></a>권장 조치

- 코드를 검토하여 필요한 경우 영향을 받는 API에 `null` 입력 인수를 전달하지 않도록 업데이트합니다.
- 코드가 <xref:System.NullReferenceException>을 처리하는 경우 <xref:System.ArgumentNullException>에 대한 처리기로 바꾸거나 추가합니다.

## <a name="affected-apis"></a>영향을 받는 API

다음 표에서는 영향을 받는 속성을 보여 줍니다.

| 속성 | 버전이 변경됨 |
|-|-|-|-|
| <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName> | 미리 보기 1 |

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->
