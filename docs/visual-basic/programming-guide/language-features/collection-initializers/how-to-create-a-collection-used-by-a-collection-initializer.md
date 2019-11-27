---
title: '방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349058"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="89c26-102">방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89c26-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="89c26-103">컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우 Visual Basic 컴파일러는 컬렉션 형식의 `Add` 메서드를 검색 하 여 `Add` 메서드의 매개 변수가 컬렉션 이니셜라이저의 값 형식과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c26-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="89c26-104">이 `Add` 메서드는 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c26-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89c26-105">예제</span><span class="sxs-lookup"><span data-stu-id="89c26-105">Example</span></span>  
 <span data-ttu-id="89c26-106">다음 예제에서는 컬렉션 이니셜라이저가 `Order`형식의 개체를 추가 하는 데 사용할 수 있는 공용 `Add` 메서드를 포함 하는 `OrderCollection` 컬렉션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89c26-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="89c26-107">`Add` 메서드를 사용 하면 축약 된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c26-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="89c26-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89c26-108">See also</span></span>

- [<span data-ttu-id="89c26-109">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="89c26-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="89c26-110">방법: 컬렉션 이니셜라이저에 사용되는 확장명 추가 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="89c26-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
