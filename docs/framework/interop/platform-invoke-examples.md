---
title: 플랫폼 호출 예제
description: User32.dll에서 MessageBox 함수를 정의하고 호출하는 방법을 보여 주는 플랫폼 호출 예제를 살펴봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 3b626061a579e089f92f2bf7de7f83f7db5bd184
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268887"
---
# <a name="platform-invoke-examples"></a>플랫폼 호출 예제

다음 예에서는 User32.dll에서 **MessageBox** 함수를 정의하고 호출하여 간단한 문자열을 인수로 전달하는 방법을 보여 줍니다. 이 예에서는 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 필드가 **Auto** 로 설정되어 있으므로 대상 플랫폼에서 문자 너비와 문자열 마샬링을 판별할 수 있습니다.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 추가 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](marshaling-data-with-platform-invoke.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [관리 코드에서 프로토타입 만들기](creating-prototypes-in-managed-code.md)
- [문자 집합 지정](specifying-a-character-set.md)
