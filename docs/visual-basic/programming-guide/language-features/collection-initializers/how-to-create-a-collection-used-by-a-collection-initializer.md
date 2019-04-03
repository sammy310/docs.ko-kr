---
title: '방법: 컬렉션 이니셜라이저 (Visual Basic)에서 사용 하는 컬렉션 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 75c280b57df03bde173c740123cccda278536dc1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820310"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="85c6a-102">방법: 컬렉션 이니셜라이저 (Visual Basic)에서 사용 하는 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="85c6a-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="85c6a-103">Visual Basic 컴파일러에 대 한 검색 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우는 `Add` 는 컬렉션 형식의 메서드 매개 변수는 `Add` 컬렉션 이니셜라이저의 값의 형식과 일치 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="85c6a-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="85c6a-104">이 `Add` 메서드 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85c6a-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c6a-105">예제</span><span class="sxs-lookup"><span data-stu-id="85c6a-105">Example</span></span>  
 <span data-ttu-id="85c6a-106">에서는 다음 예제는 `OrderCollection` 공용 포함 된 컬렉션 `Add` 형식의 개체를 추가할 컬렉션 이니셜라이저를 사용할 수 있는 메서드 `Order`합니다.</span><span class="sxs-lookup"><span data-stu-id="85c6a-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="85c6a-107">`Add` 메서드 약식된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85c6a-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="85c6a-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="85c6a-108">See also</span></span>

- [<span data-ttu-id="85c6a-109">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="85c6a-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="85c6a-110">방법: 만들기는 컬렉션 이니셜라이저에서 사용 되는 확장 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="85c6a-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
