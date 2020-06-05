---
title: 명명 지침
description: 이 개요에서는 프레임 워크 개발에 사용할 명명 규칙을 참조 하세요. 대문자 표시, 일반 이름 지정 및 기타 지침을 다루는 문서로 이동 합니다.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
ms.openlocfilehash: fbcf5ef5eb02a5e45b5c981b4247ffe1c9c2631b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447149"
---
# <a name="naming-guidelines"></a><span data-ttu-id="1ce61-104">명명 지침</span><span class="sxs-lookup"><span data-stu-id="1ce61-104">Naming Guidelines</span></span>
<span data-ttu-id="1ce61-105">프레임 워크의 개발에서 일관적인 명명 규칙 집합에 따라 프레임 워크의 유용성에 대 한 주요 기여를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-105">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="1ce61-106">이를 통해 광범위 하 게 분리 된 프로젝트에서 프레임 워크를 많은 개발자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-106">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="1ce61-107">양식의 일관성 이외에 프레임 워크 요소의 이름은 쉽게 이해 하 고 각 요소의 함수를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-107">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="1ce61-108">이 장의 목표는 개발자에 게 즉각적인 의미를 주는 이름을 지정 하는 일관 된 명명 규칙 집합을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-108">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="1ce61-109">이러한 명명 규칙을 일반 코드 개발 지침으로 적용 하면 코드 전체에서 보다 일관 된 이름이 지정 되지만 공개적으로 노출 되는 Api (공용 또는 보호 된 형식 및 멤버 및 명시적으로 구현 된 인터페이스)에만 적용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-109">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ce61-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1ce61-110">In This Section</span></span>  
 [<span data-ttu-id="1ce61-111">대문자 표기 규칙</span><span class="sxs-lookup"><span data-stu-id="1ce61-111">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="1ce61-112">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="1ce61-112">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="1ce61-113">어셈블리 및 Dll의 이름</span><span class="sxs-lookup"><span data-stu-id="1ce61-113">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="1ce61-114">네임 스페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="1ce61-114">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="1ce61-115">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="1ce61-115">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="1ce61-116">형식 멤버의 이름</span><span class="sxs-lookup"><span data-stu-id="1ce61-116">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="1ce61-117">명명 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ce61-117">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="1ce61-118">리소스 이름 지정</span><span class="sxs-lookup"><span data-stu-id="1ce61-118">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="1ce61-119">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="1ce61-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1ce61-120">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="1ce61-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce61-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ce61-121">See also</span></span>

- [<span data-ttu-id="1ce61-122">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="1ce61-122">Framework Design Guidelines</span></span>](index.md)
