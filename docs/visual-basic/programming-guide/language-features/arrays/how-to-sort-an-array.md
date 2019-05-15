---
title: '방법: Visual Basic에서 배열 정렬'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 680f488a98d6e7e31b3d077843514fd12f75481c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586435"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="d0895-102">방법: Visual Basic에서 배열 정렬</span><span class="sxs-lookup"><span data-stu-id="d0895-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="d0895-103">이 예제에서는 배열을 선언 `String` 명명 된 개체 `zooAnimals`, 채운 다음 사전순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0895-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0895-104">예제</span><span class="sxs-lookup"><span data-stu-id="d0895-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0895-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d0895-105">Compiling the Code</span></span>  
 <span data-ttu-id="d0895-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0895-106">This example requires:</span></span>  
  
- <span data-ttu-id="d0895-107">에 대 한 액세스를 <xref:System> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0895-107">Access to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d0895-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d0895-108">Robust Programming</span></span>  
 <span data-ttu-id="d0895-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d0895-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d0895-110">배열이 비어 (<xref:System.ArgumentNullException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="d0895-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
- <span data-ttu-id="d0895-111">배열이 다차원 (<xref:System.RankException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="d0895-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
- <span data-ttu-id="d0895-112">배열의 하나 이상의 요소를 구현 하지 않는 합니다 <xref:System.IComparable> 인터페이스 (<xref:System.InvalidOperationException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="d0895-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0895-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0895-113">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d0895-114">배열</span><span class="sxs-lookup"><span data-stu-id="d0895-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="d0895-115">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d0895-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="d0895-116">컬렉션</span><span class="sxs-lookup"><span data-stu-id="d0895-116">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="d0895-117">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="d0895-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
