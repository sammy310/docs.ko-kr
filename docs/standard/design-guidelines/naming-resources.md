---
title: 리소스 이름 지정
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756886"
---
# <a name="naming-resources"></a><span data-ttu-id="94c66-102">리소스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="94c66-102">Naming Resources</span></span>
<span data-ttu-id="94c66-103">지역화할 수 있는 리소스 속성 처럼 특정 개체를 통해 참조할 수, 있으므로 리소스에 대 한 명명 지침 속성 지침 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="94c66-104">**✓ DO** PascalCasing 리소스 키에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="94c66-105">**✓ DO** 설명 하는 대신 짧은 식별자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="94c66-106">**X DO NOT** 주 CLR 언어의 언어 관련 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="94c66-107">**✓ DO** 영숫자 문자와 밑줄 리소스 이름 지정 시에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="94c66-108">**✓ DO** 예외 메시지 리소스에 대 한 다음과 같은 명명 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="94c66-109">예외 형식 이름 및 예외 짧은 식별자 리소스 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c66-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="94c66-110">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="94c66-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="94c66-111">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="94c66-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c66-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="94c66-112">See also</span></span>

- [<span data-ttu-id="94c66-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="94c66-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="94c66-114">명명 지침</span><span class="sxs-lookup"><span data-stu-id="94c66-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
