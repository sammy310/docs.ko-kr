---
title: 예외 디자인 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: KrzysztofCwalina
ms.openlocfilehash: 60c3d25138c224f5eabf44d06b6c9a8373eb5f96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669057"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="d3e3d-102">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3e3d-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="d3e3d-103">예외 처리에는 반환 값에 따라 오류 보고를 통해 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e3d-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="d3e3d-104">좋은 프레임 워크로 디자인 예외의 이점을 응용 프로그램 개발자는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e3d-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="d3e3d-105">이 섹션에서는 예외의 장점을 설명 하 고 효과적으로 사용 하는 것에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e3d-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3e3d-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d3e3d-106">In This Section</span></span>  
 [<span data-ttu-id="d3e3d-107">예외 throw</span><span class="sxs-lookup"><span data-stu-id="d3e3d-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="d3e3d-108">표준 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="d3e3d-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="d3e3d-109">예외 및 성능</span><span class="sxs-lookup"><span data-stu-id="d3e3d-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="d3e3d-110">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d3e3d-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d3e3d-111">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="d3e3d-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e3d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3e3d-112">See also</span></span>

- [<span data-ttu-id="d3e3d-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d3e3d-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
