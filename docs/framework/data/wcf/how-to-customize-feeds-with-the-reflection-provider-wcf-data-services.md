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
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="d6200-103">방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d6200-103">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="d6200-104">WCF Data Services를 사용 하면 엔터티의 속성이 AtomPub 프로토콜에 정의 된 사용 하지 않은 요소에 매핑될 수 있도록 데이터 서비스 응답에서 Atom serialization을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6200-104">WCF Data Services enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="d6200-105">이 항목에서는 리플렉션 공급자를 사용하여 정의된 데이터 모델의 엔터티 형식에 대한 매핑 특성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6200-105">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="d6200-106">자세한 내용은 [피드 사용자 지정](feed-customization-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6200-106">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d6200-107">이 예제의 데이터 모델은 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](create-a-data-service-using-rp-wcf-data-services.md) 항목에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6200-107">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6200-108">예제</span><span class="sxs-lookup"><span data-stu-id="d6200-108">Example</span></span>  

 <span data-ttu-id="d6200-109">다음 예제에서는 `Order` 형식의 두 속성이 모두 기존 Atom 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6200-109">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="d6200-110">`Product`형식의 속성은 `Item` 별도의 네임 스페이스에 있는 사용자 지정 피드 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6200-110">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="d6200-111">예제</span><span class="sxs-lookup"><span data-stu-id="d6200-111">Example</span></span>  

 <span data-ttu-id="d6200-112">이전 예제에서는 URI에 대해 다음 결과를 반환 합니다 `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` .</span><span class="sxs-lookup"><span data-stu-id="d6200-112">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="d6200-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6200-113">See also</span></span>

- [<span data-ttu-id="d6200-114">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="d6200-114">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
