---
description: '자세히 알아보기: 잘못 된 패턴 문자열'
title: 잘못된 패턴 문자열
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4fbf16dd43ac4ae44e1a99d85caae4a7baf99109
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462063"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="43f6d-103">잘못된 패턴 문자열</span><span class="sxs-lookup"><span data-stu-id="43f6d-103">Invalid pattern string</span></span>

<span data-ttu-id="43f6d-104">검색의 `Like` 작업에서 지정된 패턴 문자열이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43f6d-104">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="43f6d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="43f6d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="43f6d-106">목록 식에 유효한 문자를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="43f6d-106">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="43f6d-107">패턴 범위에서 `[a-z]`처럼 범위 시작 문자가 범위 끝 문자보다 작은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43f6d-107">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="43f6d-108">패턴 범위에서 `[a--z]`처럼 여러 하이픈이 서로 인접하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43f6d-108">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="43f6d-109">닫는 대괄호를 사용하여 패턴 범위를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="43f6d-109">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f6d-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="43f6d-110">See also</span></span>

- [<span data-ttu-id="43f6d-111">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="43f6d-111">Like Operator</span></span>](../language-reference/operators/like-operator.md)
