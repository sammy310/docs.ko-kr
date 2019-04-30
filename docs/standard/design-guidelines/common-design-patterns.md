---
title: 일반 디자인 패턴
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
author: KrzysztofCwalina
ms.openlocfilehash: d0b16530863b009010383c8739c9512738dfdffd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026473"
---
# <a name="common-design-patterns"></a><span data-ttu-id="a7b7a-102">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="a7b7a-102">Common Design Patterns</span></span>
<span data-ttu-id="a7b7a-103">서적 소프트웨어 패턴, 패턴 언어 및 패턴의 매우 광범위 한 주제를 다루는 안티패턴 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="a7b7a-104">따라서이 장에서 지침 및.NET Framework Api의 디자인에서 자주 사용 되는 패턴의 매우 제한 된 집합에 관련 된 토론을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b7a-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7b7a-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a7b7a-105">In This Section</span></span>  
 [<span data-ttu-id="a7b7a-106">종속성 속성</span><span class="sxs-lookup"><span data-stu-id="a7b7a-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="a7b7a-107">삭제 패턴</span><span class="sxs-lookup"><span data-stu-id="a7b7a-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="a7b7a-108">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="a7b7a-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a7b7a-109">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="a7b7a-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b7a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7b7a-110">See also</span></span>

- [<span data-ttu-id="a7b7a-111">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a7b7a-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
