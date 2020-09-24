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
ms.openlocfilehash: fb22e87569a8e243813b3186232b6989abeb2a5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161310"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="03d77-102">방법: 리플렉션 공급자를 사용한 피드 사용자 지정(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="03d77-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>

<span data-ttu-id="03d77-103">WCF Data Services를 사용 하면 엔터티의 속성이 AtomPub 프로토콜에 정의 된 사용 하지 않은 요소에 매핑될 수 있도록 데이터 서비스 응답에서 Atom serialization을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d77-103">WCF Data Services enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="03d77-104">이 항목에서는 리플렉션 공급자를 사용하여 정의된 데이터 모델의 엔터티 형식에 대한 매핑 특성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03d77-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="03d77-105">자세한 내용은 [피드 사용자 지정](feed-customization-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03d77-105">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="03d77-106">이 예제의 데이터 모델은 [방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기](create-a-data-service-using-rp-wcf-data-services.md) 항목에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d77-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="03d77-107">예제</span><span class="sxs-lookup"><span data-stu-id="03d77-107">Example</span></span>  

 <span data-ttu-id="03d77-108">다음 예제에서는 `Order` 형식의 두 속성이 모두 기존 Atom 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="03d77-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="03d77-109">`Product`형식의 속성은 `Item` 별도의 네임 스페이스에 있는 사용자 지정 피드 특성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="03d77-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="03d77-110">예제</span><span class="sxs-lookup"><span data-stu-id="03d77-110">Example</span></span>  

 <span data-ttu-id="03d77-111">이전 예제에서는 URI에 대해 다음 결과를 반환 합니다 `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` .</span><span class="sxs-lookup"><span data-stu-id="03d77-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="03d77-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03d77-112">See also</span></span>

- [<span data-ttu-id="03d77-113">리플렉션 공급자</span><span class="sxs-lookup"><span data-stu-id="03d77-113">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
