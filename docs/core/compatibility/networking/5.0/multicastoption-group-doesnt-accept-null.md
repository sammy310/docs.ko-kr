---
title: '호환성이 손상되는 변경: MulticastOption.Group에서 null 값을 허용하지 않음'
description: MulticastOption.Group에서 Null 값을 더 이상 허용하지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 08/18/2020
ms.openlocfilehash: 09c6415d275361abee8285aabdda13ccd9727043
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256454"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group에서 null 값을 허용하지 않음

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>에서는 `null` 값을 더 이상 허용하지 않습니다. 속성을 `null`로 설정하면 <xref:System.ArgumentNullException>이 throw됩니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET에서는 <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> 속성을 `null`로 설정할 수 있습니다. 나중에 <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>에 <xref:System.Net.Sockets.MulticastOption>을 전달하면 런타임에서 <xref:System.NullReferenceException>이 throw됩니다.

.NET 5 이상에서 속성을 `null`로 설정하면 <xref:System.ArgumentNullException>이 throw됩니다.

## <a name="reason-for-change"></a>변경 이유

프레임워크 디자인 지침과 일치하도록, 값이 `null`이면 <xref:System.ArgumentNullException>을 throw하도록 속성이 업데이트되었습니다.

## <a name="recommended-action"></a>권장 조치

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>을 `null`으로 설정하지 않도록 합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
