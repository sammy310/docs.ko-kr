---
title: Visual Basic의 Nothing 및 문자열
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841890"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="ee5ef-102">Visual Basic의 Nothing 및 문자열</span><span class="sxs-lookup"><span data-stu-id="ee5ef-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="ee5ef-103">Visual Basic 런타임 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 평가 `Nothing` 다르게는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="ee5ef-104">Visual Basic 런타임 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee5ef-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="ee5ef-105">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="ee5ef-106">Visual Basic 런타임 일반적으로 평가 `Nothing` 을 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="ee5ef-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="ee5ef-107">그러나 합니다 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 하지 않는 문자열 작업을 수행 하려고 시도 될 때마다 예외를 throw 및 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5ef-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee5ef-108">See also</span></span>

- [<span data-ttu-id="ee5ef-109">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="ee5ef-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
