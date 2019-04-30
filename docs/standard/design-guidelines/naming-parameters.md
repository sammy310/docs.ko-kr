---
title: 매개 변수 이름 지정
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026313"
---
# <a name="naming-parameters"></a><span data-ttu-id="10928-102">매개 변수 이름 지정</span><span class="sxs-lookup"><span data-stu-id="10928-102">Naming Parameters</span></span>
<span data-ttu-id="10928-103">가독성의 이유를 초과 비주얼 디자인 도구 Intellisense 및 검색 기능을 하는 클래스를 제공 하는 경우 매개 변수는 문서에 디자이너에 표시 되기 때문에 매개 변수 이름에 대 한 지침을 따르는 것이 반드시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10928-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="10928-104">**✓ DO** camelCasing 매개 변수 이름에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10928-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="10928-105">**✓ DO** 설명이 포함 된 매개 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10928-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="10928-106">**✓ CONSIDER** 매개 변수의 형식 보다는 매개 변수의 의미에 따라 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10928-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="10928-107">연산자 오버 로드 매개 변수 이름 지정</span><span class="sxs-lookup"><span data-stu-id="10928-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="10928-108">**✓ DO** 사용 `left` 및 `right` 이항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="10928-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="10928-109">**✓ DO** 사용 `value` 에 대 한 단항 연산자 오버 로드 매개 변수 이름은 매개 변수를 아무 의미가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="10928-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="10928-110">**✓ CONSIDER** 연산자에 대 한 의미 있는 이름을 추가 되므로 중요 한 가치 경우 매개 변수를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="10928-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="10928-111">**X DO NOT** 오버 로드 매개 변수 이름을 사용 하 여 약어 또는 연산자에 대 한 숫자 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="10928-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="10928-112">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="10928-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="10928-113">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="10928-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10928-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="10928-114">See also</span></span>

- [<span data-ttu-id="10928-115">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="10928-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="10928-116">명명 지침</span><span class="sxs-lookup"><span data-stu-id="10928-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
