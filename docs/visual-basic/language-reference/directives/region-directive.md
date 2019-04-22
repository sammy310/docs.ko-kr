---
title: '#Region 지시문 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: eaaf0f8279ec905767be3f364a88357f0d393bba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818878"
---
# <a name="region-directive"></a><span data-ttu-id="b759a-102">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="b759a-102">#Region Directive</span></span>
<span data-ttu-id="b759a-103">Visual Basic 파일에서 코드 섹션을 축소하고 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b759a-104">구문</span><span class="sxs-lookup"><span data-stu-id="b759a-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="b759a-105">요소</span><span class="sxs-lookup"><span data-stu-id="b759a-105">Parts</span></span>  
  
|<span data-ttu-id="b759a-106">용어</span><span class="sxs-lookup"><span data-stu-id="b759a-106">Term</span></span>|<span data-ttu-id="b759a-107">정의</span><span class="sxs-lookup"><span data-stu-id="b759a-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="b759a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b759a-108">Required.</span></span> <span data-ttu-id="b759a-109">축소된 경우 영역의 제목 역할을 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="b759a-110">영역은 기본적으로 축소되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="b759a-111">`#Region` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b759a-112">설명</span><span class="sxs-lookup"><span data-stu-id="b759a-112">Remarks</span></span>  
 <span data-ttu-id="b759a-113">`#Region` 지시문을 사용하면 Visual Studio 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="b759a-114">배치할 수 있습니다 또는 *중첩*, 비슷한 영역을 함께 그룹화 할 다른 지역 내의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b759a-115">예제</span><span class="sxs-lookup"><span data-stu-id="b759a-115">Example</span></span>  
 <span data-ttu-id="b759a-116">이 예제에서는 `#Region` 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b759a-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b759a-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b759a-117">See also</span></span>

- [<span data-ttu-id="b759a-118">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="b759a-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="b759a-119">개요</span><span class="sxs-lookup"><span data-stu-id="b759a-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="b759a-120">방법: 코드 섹션 축소 및 숨기기</span><span class="sxs-lookup"><span data-stu-id="b759a-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
