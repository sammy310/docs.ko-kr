---
description: '자세한 정보: 예외 디자인 지침'
title: 예외 디자인 지침
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: 0845f06dca0ee83d7315c3b0b4b6ae090b24a875
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642112"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="ed938-103">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ed938-103">Design Guidelines for Exceptions</span></span>

<span data-ttu-id="ed938-104">예외 처리는 반환 값 기반 오류 보고와 비교하여 여러 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed938-104">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="ed938-105">바람직한 프레임워크 디자인은 애플리케이션 개발자가 예외의 이점을 실현하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed938-105">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="ed938-106">이 섹션에서는 예외의 이점에 대해 설명하고 이러한 예외의 효과적 사용에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed938-106">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed938-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ed938-107">In This Section</span></span>  

 [<span data-ttu-id="ed938-108">예외 throw</span><span class="sxs-lookup"><span data-stu-id="ed938-108">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="ed938-109">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="ed938-109">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="ed938-110">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="ed938-110">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="ed938-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="ed938-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ed938-112">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ed938-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed938-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed938-113">See also</span></span>

- [<span data-ttu-id="ed938-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ed938-114">Framework Design Guidelines</span></span>](index.md)
