---
title: '방법: 컬렉션 이니셜라이저에서 사용되는 확장 메서드 만들기 및 추가'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 4dbe6146b70181864a6717146071f9b93a1f583e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414571"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="65229-102">방법: 컬렉션 이니셜라이저에 사용되는 확장 추가 메서드 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65229-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="65229-103">컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우 Visual Basic 컴파일러는 컬렉션 형식의 메서드를 검색 합니다 .이 메서드는 컬렉션의 `Add` 매개 변수가 `Add` 컬렉션 이니셜라이저의 값 형식과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="65229-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="65229-104">이 메서드는 컬렉션을 `Add` 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65229-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="65229-105">일치 하는 `Add` 메서드가 없고 컬렉션에 대 한 코드를 수정할 수 없는 경우 `Add` 컬렉션 이니셜라이저에 필요한 매개 변수를 사용 하는 라는 확장명 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65229-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="65229-106">일반적으로 제네릭 컬렉션에 대해 컬렉션 이니셜라이저를 사용할 때 수행 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="65229-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65229-107">예제</span><span class="sxs-lookup"><span data-stu-id="65229-107">Example</span></span>  
 <span data-ttu-id="65229-108">다음 예제에서는 <xref:System.Collections.Generic.List%601> 컬렉션 이니셜라이저를 사용 하 여 형식의 개체를 추가할 수 있도록 제네릭 형식에 확장 메서드를 추가 하는 방법을 보여 줍니다 `Employee` .</span><span class="sxs-lookup"><span data-stu-id="65229-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="65229-109">확장 메서드를 사용 하면 축약 된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65229-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="65229-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65229-110">See also</span></span>

- [<span data-ttu-id="65229-111">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="65229-111">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="65229-112">방법: 컬렉션 이니셜라이저에서 사용되는 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="65229-112">How to: Create a Collection Used by a Collection Initializer</span></span>](how-to-create-a-collection-used-by-a-collection-initializer.md)
