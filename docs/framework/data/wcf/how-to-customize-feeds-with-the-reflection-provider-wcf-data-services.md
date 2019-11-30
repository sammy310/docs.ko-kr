---
title: '방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: d3e2d587978a4c82784c8cfc8a7acc17cf601c3a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569140"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)
WCF Data Services를 사용 하면 엔터티의 속성이 AtomPub 프로토콜에 정의 된 사용 하지 않은 요소에 매핑될 수 있도록 데이터 서비스 응답에서 Atom serialization을 사용자 지정할 수 있습니다. 이 항목에서는 리플렉션 공급자를 사용하여 정의된 데이터 모델의 엔터티 형식에 대한 매핑 특성을 정의하는 방법을 보여 줍니다. 자세한 내용은 [피드 사용자 지정](feed-customization-wcf-data-services.md)을 참조 하세요.  
  
 이 예제의 데이터 모델은 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](create-a-data-service-using-rp-wcf-data-services.md) 항목에 정의 되어 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Order` 형식의 두 속성이 모두 기존 Atom 요소에 매핑됩니다. `Item` 형식의 `Product` 속성은 별도의 네임 스페이스에 있는 사용자 지정 피드 특성에 매핑됩니다.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>예제  
 이전 예에서는 `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`URI에 대해 다음 결과를 반환 합니다.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>참조

- [리플렉션 공급자](reflection-provider-wcf-data-services.md)
