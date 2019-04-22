---
title: Assembly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819257"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="46013-102">Assembly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46013-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="46013-103">소스 파일의 시작 부분에 있는 특성이 전체 어셈블리에 적용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46013-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46013-104">설명</span><span class="sxs-lookup"><span data-stu-id="46013-104">Remarks</span></span>  
 <span data-ttu-id="46013-105">많은 특성이 클래스나 속성 같은 개별 프로그래밍 요소에 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46013-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="46013-106">꺾쇠 괄호를 특성 블록을 연결 하 여 특성을 적용 하면 (`< >`), 선언문에 직접.</span><span class="sxs-lookup"><span data-stu-id="46013-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="46013-107">특성에는 다음 요소 뿐 아니라 전체 어셈블리에 관련 된, 소스 파일의 시작 부분에 특성 블록을 배치를 사용 하 여 특성을 식별 합니다 `Assembly` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="46013-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="46013-108">현재 어셈블리 모듈에 해당 되는 경우 사용 합니다 [모듈](../../../visual-basic/language-reference/modifiers/module-keyword.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="46013-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="46013-109">적용할 수 있습니다도 특성 AssemblyInfo.vb 파일에서 어셈블리에 경우 특성 블록을 사용 하 여 주 소스 코드 파일에서 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46013-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46013-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="46013-110">See also</span></span>

- [<span data-ttu-id="46013-111">모듈 \<키워드></span><span class="sxs-lookup"><span data-stu-id="46013-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="46013-112">특성 개요</span><span class="sxs-lookup"><span data-stu-id="46013-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
