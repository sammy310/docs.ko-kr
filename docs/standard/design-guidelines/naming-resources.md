---
title: 리소스 이름 지정
description: 속성 명명 지침과 비슷한 .NET의 리소스에 대 한 명명 지침을 검토 합니다.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: c01e041edbf30813c477e579867abb9099ce0528
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820854"
---
# <a name="naming-resources"></a><span data-ttu-id="9e75f-103">리소스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="9e75f-103">Naming Resources</span></span>
<span data-ttu-id="9e75f-104">지역화할 수 있는 리소스는 속성과 같이 특정 개체를 통해 참조 될 수 있기 때문에 리소스에 대 한 명명 지침은 속성 지침과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-104">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="9e75f-105">리소스 키에 대 한 대/소문자 구분을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-105">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="9e75f-106">✔️ 짧은 식별자 대신 설명이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-106">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="9e75f-107">❌ 주요 CLR 언어의 언어별 키워드를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="9e75f-107">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="9e75f-108">✔️는 리소스 이름 지정에 영숫자 문자와 밑줄만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-108">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="9e75f-109">예외 메시지 리소스에는 다음 명명 규칙을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-109">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="9e75f-110">리소스 식별자는 예외 형식 이름 및 예외의 짧은 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e75f-110">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="9e75f-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="9e75f-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="9e75f-112">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="9e75f-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9e75f-113">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="9e75f-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9e75f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e75f-114">See also</span></span>

- [<span data-ttu-id="9e75f-115">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="9e75f-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="9e75f-116">명명 지침</span><span class="sxs-lookup"><span data-stu-id="9e75f-116">Naming Guidelines</span></span>](naming-guidelines.md)
