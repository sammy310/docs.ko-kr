---
description: '자세히 알아보기: 방법: 리플렉션 공급자를 사용 하 여 피드 사용자 지정 (WCF Data Services)'
title: '방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 91ac9cd3a5e882714335ce1d4ef29510d4640534
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765635"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

WCF Data Services를 사용 하면 엔터티의 속성이 AtomPub 프로토콜에 정의 된 사용 하지 않은 요소에 매핑될 수 있도록 데이터 서비스 응답에서 Atom serialization을 사용자 지정할 수 있습니다. 이 항목에서는 리플렉션 공급자를 사용하여 정의된 데이터 모델의 엔터티 형식에 대한 매핑 특성을 정의하는 방법을 보여 줍니다. 자세한 내용은 [피드 사용자 지정](feed-customization-wcf-data-services.md)을 참조 하세요.  
  
 이 예제의 데이터 모델은 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](create-a-data-service-using-rp-wcf-data-services.md) 항목에 정의 되어 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `Order` 형식의 두 속성이 모두 기존 Atom 요소에 매핑됩니다. `Product`형식의 속성은 `Item` 별도의 네임 스페이스에 있는 사용자 지정 피드 특성에 매핑됩니다.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>예제  

 이전 예제에서는 URI에 대해 다음 결과를 반환 합니다 `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` .  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>참고 항목

- [리플렉션 공급자](reflection-provider-wcf-data-services.md)
