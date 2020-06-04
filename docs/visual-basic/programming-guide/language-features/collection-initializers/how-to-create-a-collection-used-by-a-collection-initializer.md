---
title: '방법: 컬렉션 이니셜라이저에서 사용되는 컬렉션 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 7cba290b92f41125a93d1ed022e4db5ef62da789
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414558"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="04c6f-102">방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04c6f-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="04c6f-103">컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우 Visual Basic 컴파일러는 컬렉션 형식의 메서드를 검색 합니다 .이 메서드는 컬렉션의 `Add` 매개 변수가 `Add` 컬렉션 이니셜라이저의 값 형식과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="04c6f-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="04c6f-104">이 메서드는 컬렉션을 `Add` 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04c6f-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04c6f-105">예제</span><span class="sxs-lookup"><span data-stu-id="04c6f-105">Example</span></span>  
 <span data-ttu-id="04c6f-106">다음 예제에서는 `OrderCollection` `Add` 컬렉션 이니셜라이저가 형식의 개체를 추가 하는 데 사용할 수 있는 공용 메서드를 포함 하는 컬렉션을 보여 줍니다 `Order` .</span><span class="sxs-lookup"><span data-stu-id="04c6f-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="04c6f-107">`Add`메서드를 사용 하면 축약 된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c6f-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="04c6f-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04c6f-108">See also</span></span>

- [<span data-ttu-id="04c6f-109">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="04c6f-109">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="04c6f-110">방법: 컬렉션 이니셜라이저에서 사용되는 확장 메서드 만들기 및 추가</span><span class="sxs-lookup"><span data-stu-id="04c6f-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
