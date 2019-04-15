---
title: '방법: 어셈블리에서 형식 및 멤버 정보 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f9d01715a9635b276ca87d94082bb4d3820084e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138881"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>방법: 어셈블리에서 형식 및 멤버 정보 가져오기
<xref:System.Reflection> 네임스페이스에는 어셈블리에서 정보를 가져오는 다양한 메서드가 포함되어 있습니다. 이 섹션에서는 이러한 메서드 중 하나를 보여 줍니다. 자세한 내용은 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)를 참조하세요.  
  
 다음 예제에서는 어셈블리에서 형식 및 멤버 정보를 가져옵니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>참고 항목

- [애플리케이션 도메인으로 프로그래밍](./application-domains.md#programming-with-application-domains)
- [반사](../../../docs/framework/reflection-and-codedom/reflection.md)
- [애플리케이션 도메인 사용](../../../docs/framework/app-domains/use.md)
