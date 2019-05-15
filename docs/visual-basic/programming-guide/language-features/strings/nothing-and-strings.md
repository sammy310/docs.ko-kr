---
title: Visual Basic의 Nothing 및 문자열
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591351"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="cbd43-102">Visual Basic의 Nothing 및 문자열</span><span class="sxs-lookup"><span data-stu-id="cbd43-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="cbd43-103">Visual Basic 런타임 및.NET Framework 평가 `Nothing` 다르게는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cbd43-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="cbd43-104">Visual Basic 런타임 및.NET Framework</span><span class="sxs-lookup"><span data-stu-id="cbd43-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="cbd43-105">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbd43-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="cbd43-106">Visual Basic 런타임 일반적으로 평가 `Nothing` 을 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="cbd43-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="cbd43-107">하지만.NET Framework 않습니다, 및 문자열 작업을 수행 하려고 시도 될 때마다 예외를 throw `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd43-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd43-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbd43-108">See also</span></span>

- [<span data-ttu-id="cbd43-109">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="cbd43-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
