---
title: 매개 변수 이름 지정
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709181"
---
# <a name="naming-parameters"></a><span data-ttu-id="c8beb-102">매개 변수 이름 지정</span><span class="sxs-lookup"><span data-stu-id="c8beb-102">Naming Parameters</span></span>
<span data-ttu-id="c8beb-103">시각적 디자인 도구에서 Intellisense 및 클래스 검색 기능을 제공 하는 경우 매개 변수가 설명서 및 디자이너에 표시 되기 때문에 가독성을 명확 하 게 이해 하는 것은 매개 변수 이름에 대 한 지침을 따르는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="c8beb-104">**✓ DO** camelCasing 매개 변수 이름에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="c8beb-105">**✓ DO** 설명이 포함 된 매개 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="c8beb-106">**✓ CONSIDER** 매개 변수의 형식 보다는 매개 변수의 의미에 따라 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="c8beb-107">명명 연산자 오버 로드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8beb-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="c8beb-108">**✓ DO** 사용 `left` 및 `right` 이항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="c8beb-109">**✓ DO** 사용 `value` 에 대 한 단항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="c8beb-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="c8beb-110">**✓ CONSIDER** 연산자에 대 한 의미 있는 이름을 추가 되므로 중요 한 가치 경우 매개 변수를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="c8beb-111">**X DO NOT** 오버 로드 매개 변수 이름을 사용 하 여 약어 또는 연산자에 대 한 숫자 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8beb-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="c8beb-112">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="c8beb-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c8beb-113">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c8beb-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8beb-114">참조</span><span class="sxs-lookup"><span data-stu-id="c8beb-114">See also</span></span>

- [<span data-ttu-id="c8beb-115">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="c8beb-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c8beb-116">명명 지침</span><span class="sxs-lookup"><span data-stu-id="c8beb-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
