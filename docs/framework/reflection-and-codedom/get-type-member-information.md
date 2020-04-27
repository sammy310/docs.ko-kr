---
title: '방법: 리플렉션을 사용하여 형식 및 멤버 정보 가져오기'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 9ffc173bbd0ed12eedea0c191f6d39baf181793a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130210"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>방법: 리플렉션을 사용하여 형식 및 멤버 정보 가져오기
<xref:System.Reflection> 네임스페이스에는 형식 및 멤버에 관한 정보를 가져오는 여러 메서드가 포함되어 있습니다. 이 문서에서는 이러한 메서드 중 하나인 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>을 보여 줍니다. 자세한 내용은 [리플렉션 개요](reflection.md)를 참조하세요.
  
## <a name="example"></a>예제

다음 예제에서는 리플렉션을 사용하여 형식 및 멤버 정보를 가져옵니다.

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>참조

- [애플리케이션 도메인으로 프로그래밍](../app-domains/application-domains.md#programming-with-application-domains)
- [리플렉션](reflection.md)
- [애플리케이션 도메인 사용](../app-domains/use.md)
