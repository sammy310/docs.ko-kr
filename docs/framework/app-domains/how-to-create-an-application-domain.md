---
title: '방법: 애플리케이션 도메인 만들기'
description: .NET에서 애플리케이션 도메인을 만드는 방법을 검토합니다. 개인적으로 관리할 어셈블리를 로드할 애플리케이션 도메인을 만들거나 코드를 실행할 애플리케이션 도메인을 만들 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: fb022511ee395a9312e4dbaf7c0beee03c9b4569
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264090"
---
# <a name="how-to-create-an-application-domain"></a>방법: 애플리케이션 도메인 만들기

공용 언어 런타임 호스트는 필요할 때 자동으로 애플리케이션 도메인을 만듭니다. 그러나 사용자 고유의 애플리케이션 도메인을 만들고 개인적으로 관리하려는 어셈블리를 해당 도메인에 로드할 수 있습니다. 코드를 실행할 애플리케이션 도메인을 만들 수도 있습니다.  
  
 <xref:System.AppDomain?displayProperty=nameWithType> 클래스에 오버로드된 **CreateDomain** 메서드 중 하나를 사용하여 새 애플리케이션 도메인을 만듭니다. 애플리케이션 도메인에 이름을 지정하고 해당 이름으로 참조할 수 있습니다.  
  
 다음 예제에서는 새 애플리케이션 도메인을 만들고, 이름 `MyDomain`을 할당한 다음 호스트 도메인 및 새로 만든 자식 애플리케이션 도메인의 이름을 콘솔에 출력합니다.  
  
## <a name="example"></a>예제  

 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>참조

- [애플리케이션 도메인으로 프로그래밍](application-domains.md#programming-with-application-domains)
- [애플리케이션 도메인 사용](use.md)
