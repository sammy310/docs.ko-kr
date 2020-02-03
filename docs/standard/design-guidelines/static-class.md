---
title: 정적 클래스 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 104fa204a95ef31d34e224348068e3a6505aded5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743600"
---
# <a name="static-class-design"></a><span data-ttu-id="2f541-102">정적 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="2f541-102">Static Class Design</span></span>
<span data-ttu-id="2f541-103">정적 클래스는 정적 멤버만 포함 하는 클래스로 정의 됩니다. 예를 들어 <xref:System.Object?displayProperty=nameWithType>에서 상속 되는 인스턴스 멤버 외에도 전용 생성자가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="2f541-104">일부 언어에서는 정적 클래스에 대 한 기본 제공 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="2f541-105">2\.0 C# 이상에서 클래스가 정적으로 선언 되 면 sealed, abstract 이며 인스턴스 멤버를 재정의 하거나 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>

 <span data-ttu-id="2f541-106">정적 클래스는 순수 개체 지향 디자인과 단순성 간의 손상입니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="2f541-107">이러한 메서드는 일반적으로 다른 작업 (예: <xref:System.IO.File?displayProperty=nameWithType>), 확장 메서드 소유자 또는 전체 개체 지향 래퍼 (<xref:System.Environment?displayProperty=nameWithType>)가 불필요 한 상승을 기능에 대 한 바로 가기를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="2f541-108">✔️는 정적 클래스를 자주 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-108">✔️ DO use static classes sparingly.</span></span>

 <span data-ttu-id="2f541-109">정적 클래스는 프레임 워크의 개체 지향 코어에 대 한 지원 클래스로만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>

 <span data-ttu-id="2f541-110">정적 클래스를 기타 버킷으로 처리 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="2f541-110">❌ DO NOT treat static classes as a miscellaneous bucket.</span></span>

 <span data-ttu-id="2f541-111">❌ 정적 클래스의 인스턴스 멤버를 선언 하거나 재정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-111">❌ DO NOT declare or override instance members in static classes.</span></span>

 <span data-ttu-id="2f541-112">정적 클래스를 기본적으로 지원 하지 않는 경우 정적 클래스를 sealed, abstract로 선언 하 고 전용 인스턴스 생성자를 추가 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f541-112">✔️ DO declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>

 <span data-ttu-id="2f541-113">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="2f541-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2f541-114">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2f541-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2f541-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f541-115">See also</span></span>

- [<span data-ttu-id="2f541-116">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="2f541-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="2f541-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="2f541-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
