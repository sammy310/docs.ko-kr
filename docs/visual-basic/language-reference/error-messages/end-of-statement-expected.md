---
title: 문의 끝이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 9141400afc651629df381e0a655e2d7b9da2e45d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874418"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="57f24-102">문의 끝이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-102">End of statement expected</span></span>

<span data-ttu-id="57f24-103">구문이 완전 하지만 문이 완료 된 요소 다음에 추가 프로그래밍 요소가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="57f24-104">줄 종결자는 모든 문 끝에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="57f24-105">줄 종결자는 Visual Basic 소스 파일의 문자를 줄로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="57f24-106">줄 종결자의 예로는 유니코드 캐리지 리턴 문자 (&HD), 유니코드 줄 바꿈 문자 (&HA), 유니코드 캐리지 리턴 문자, 유니코드 줄 바꿈 문자가 차례로 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="57f24-107">줄 종결자에 대 한 자세한 내용은 [Visual Basic 언어 사양](~/_vblang/spec/lexical-grammar.md#line-terminators)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57f24-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="57f24-108">**오류 ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="57f24-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57f24-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="57f24-109">To correct this error</span></span>
  
1. <span data-ttu-id="57f24-110">서로 다른 두 문이 실수로 같은 줄에 배치 되었는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="57f24-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="57f24-111">문을 완료 하는 요소 뒤에 줄 종결자를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f24-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57f24-112">참조</span><span class="sxs-lookup"><span data-stu-id="57f24-112">See also</span></span>

- [<span data-ttu-id="57f24-113">방법: 코드에서 명령문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="57f24-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="57f24-114">문</span><span class="sxs-lookup"><span data-stu-id="57f24-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
