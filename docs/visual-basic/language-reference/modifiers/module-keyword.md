---
description: '자세한 정보: 모듈 <keyword> (Visual Basic)'
title: 모듈 <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 1bd25b00b41f5da4fca535220fe4e1694c81baca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640695"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="b2ea9-103">Module \<keyword>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2ea9-103">Module \<keyword> (Visual Basic)</span></span>

<span data-ttu-id="b2ea9-104">소스 파일의 시작 부분에 있는 특성이 현재 어셈블리 모듈에 적용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ea9-104">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2ea9-105">설명</span><span class="sxs-lookup"><span data-stu-id="b2ea9-105">Remarks</span></span>  

 <span data-ttu-id="b2ea9-106">많은 특성은 클래스 또는 속성과 같은 개별 프로그래밍 요소와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ea9-106">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="b2ea9-107">꺾쇠 괄호 () 내에서 선언 문에 직접 특성 블록을 연결 하 여 이러한 특성을 적용 `< >` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ea9-107">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="b2ea9-108">특성이 다음 요소 뿐만 아니라 현재 어셈블리 모듈에만 관련 되는 경우 특성 블록을 소스 파일의 시작 부분에 놓고 키워드를 사용 하 여 특성을 식별 합니다 `Module` .</span><span class="sxs-lookup"><span data-stu-id="b2ea9-108">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="b2ea9-109">전체 어셈블리에 적용 되는 경우 [assembly](assembly.md) 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ea9-109">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="b2ea9-110">`Module`한정자는 [Module 문과](../statements/module-statement.md)다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b2ea9-110">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ea9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2ea9-111">See also</span></span>

- [<span data-ttu-id="b2ea9-112">어셈블리</span><span class="sxs-lookup"><span data-stu-id="b2ea9-112">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="b2ea9-113">Module 문</span><span class="sxs-lookup"><span data-stu-id="b2ea9-113">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="b2ea9-114">특성 개요</span><span class="sxs-lookup"><span data-stu-id="b2ea9-114">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
