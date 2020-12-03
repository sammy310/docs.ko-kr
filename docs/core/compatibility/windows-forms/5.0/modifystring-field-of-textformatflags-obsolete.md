---
title: '호환성이 손상되는 변경: TextFormatFlags.ModifyString은 사용되지 않음'
description: TextFormatFlags.ModifyString 필드가 경고로 사용되지 않는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759680"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a>TextFormatFlags.ModifyString은 사용되지 않음

<xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 필드는 경고로 사용되지 않으며 이후 .NET 버전에서 제거될 수 있습니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 열거형 필드는 사용되지 않음으로 표시되지 않습니다. .NET 5.0 이상 버전에서는 경고로 사용되지 않는 것으로 표시됩니다. 이 필드는 이후 .NET 버전에서 제거될 수 있습니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>을 사용하여 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType>에 문자열을 전달하면 일부 상황에서 문자열이 변경됩니다. 이 동작으로 인해 문자열 불변성 프라미스가 위반되고 .NET 런타임 상태가 심각하게 손상될 수 있습니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

<xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>에 의존하는 모든 코드를 업데이트합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
