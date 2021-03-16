---
title: SYSLIB0005 경고
description: 컴파일 시간 경고 SYSLIB0005를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9ed36d247d31bcebc499bd7ed3945490d9d901f9
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256372"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a>SYSLIB0005: GAC(전역 어셈블리 캐시)가 지원되지 않음

.NET Core 및 .NET 5 이상 버전에서는 .NET Framework에 있었던 GAC(전역 어셈블리 캐시) 개념이 사라집니다. 개발자가 이러한 API를 사용하지 않도록 하기 위해 .NET 5.0부터 일부 GAC 관련 API는 사용되지 않는 것으로 표시됩니다. 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0005` 경고가 생성됩니다.

다음은 사용되지 않는 것으로 표시되는 GAC 관련 API입니다.

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  라이브러리와 앱은 런타임 동작에 대한 결정을 내릴 때 <xref:System.Reflection.Assembly.GlobalAssemblyCache> API를 사용하면 안 됩니다. 이 API는 .NET Core 및 .NET 5+에서 항상 `false`를 반환하기 때문입니다.

## <a name="workarounds"></a>해결 방법

애플리케이션이 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성을 쿼리하는 경우 호출을 제거하는 것이 좋습니다. <xref:System.Reflection.Assembly.GlobalAssemblyCache> 값을 사용하여 런타임에 “GAC의 어셈블리” 흐름과 “GAC에 없는 어셈블리” 흐름을 선택하는 경우 이 흐름이 .NET 5+ 애플리케이션에 적합한지 여부를 재고해야 합니다.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>참조

- [전역 어셈블리 캐시](../../../framework/app-domains/gac.md)
