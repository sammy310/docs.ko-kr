---
title: '방법: 만들기는 컬렉션 이니셜라이저 (Visual Basic)를 사용 하는 확장 메서드를 추가 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907077"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="3dcde-102">방법: 만들기는 컬렉션 이니셜라이저 (Visual Basic)를 사용 하는 확장 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="3dcde-103">Visual Basic 컴파일러에 대 한 검색 컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우는 `Add` 는 컬렉션 형식의 메서드 매개 변수는 `Add` 컬렉션 이니셜라이저의 값의 형식과 일치 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="3dcde-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="3dcde-104">이 `Add` 메서드 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="3dcde-105">일치 하는 경우 `Add` 메서드 및 컬렉션에 대 한 코드를 수정할 수 없습니다, 확장 메서드를 추가할 수 있습니다 `Add` 컬렉션 이니셜라이저에 필요한 매개 변수를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="3dcde-106">일반적으로 이것이 컬렉션 이니셜라이저를 사용 하 여 제네릭 컬렉션 용 때 수행할 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dcde-107">예제</span><span class="sxs-lookup"><span data-stu-id="3dcde-107">Example</span></span>  
 <span data-ttu-id="3dcde-108">다음 예제에서는 제네릭 확장 메서드를 추가 하는 방법을 보여 줍니다 <xref:System.Collections.Generic.List%601> 형식의 개체를 추가할 컬렉션 이니셜라이저를 사용할 수 있도록 입력 `Employee`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="3dcde-109">확장 메서드를 사용 하면 축약된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dcde-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3dcde-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="3dcde-110">See also</span></span>

- [<span data-ttu-id="3dcde-111">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="3dcde-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="3dcde-112">방법: 컬렉션 이니셜라이저에서 사용 되는 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="3dcde-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
