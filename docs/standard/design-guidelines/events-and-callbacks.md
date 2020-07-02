---
title: 이벤트 및 콜백
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 4000944c3b913f71bc18462cea9062e9237ae53f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619535"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="13a94-102">이벤트 및 콜백</span><span class="sxs-lookup"><span data-stu-id="13a94-102">Events and Callbacks</span></span>
<span data-ttu-id="13a94-103">콜백은 프레임 워크가 대리자를 통해 사용자 코드를 다시 호출할 수 있도록 하는 확장성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="13a94-104">이러한 대리자는 일반적으로 메서드의 매개 변수를 통해 프레임 워크에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="13a94-105">이벤트는 대리자 (이벤트 처리기)를 제공 하기 위한 편리 하 고 일관적인 구문을 지 원하는 특수 한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="13a94-106">또한 Visual Studio의 문 완성 및 디자이너는 이벤트 기반 Api 사용에 대 한 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-106">In addition, Visual Studio's statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="13a94-107">[이벤트 디자인](event.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13a94-107">(See [Event Design](event.md).)</span></span>

 <span data-ttu-id="13a94-108">사용자가 프레임 워크에서 실행할 사용자 지정 코드를 제공할 수 있도록 콜백을 사용 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="13a94-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="13a94-109">✔️ 이벤트를 사용 하 여 개체 지향 디자인을 이해 하지 않고도 프레임 워크의 동작을 사용자 지정할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="13a94-110">일반 콜백에 대 한 이벤트를 사용 하는 것이 더 광범위 한 개발자에 게 더 친숙 하 고 Visual Studio 문 완성 기능과 통합 되어 있기 때문에 ✔️.</span><span class="sxs-lookup"><span data-stu-id="13a94-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="13a94-111">❌성능에 민감한 Api에서 콜백을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="13a94-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="13a94-112">✔️는 `Func<...>` `Action<...>` `Expression<...>` 콜백을 사용 하 여 api를 정의할 때 사용자 지정 대리자 대신 새, 또는 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="13a94-113">`Func<...>`및는 `Action<...>` 제네릭 대리자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="13a94-114">`Expression<...>`런타임에 컴파일되고 나중에 호출할 수 있는 함수 정의를 나타내며 serialize 되어 원격 프로세스에 전달 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="13a94-115">및 대리자를 사용 하는 대신를 사용 하는 경우의 성능 영향을 측정 하 고 이해 ✔️ `Expression<...>` `Func<...>` `Action<...>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="13a94-116">`Expression<...>`형식은 대부분의 경우 `Func<...>` 및 대리자와 논리적으로 동일 `Action<...>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="13a94-117">이러한 두 가지 주요 차이점은 대리자는 로컬 프로세스 시나리오에서 사용 하기 위한 것입니다. 식은 원격 프로세스나 컴퓨터에서 식을 평가 하는 데 유용 하 고 사용할 수 있는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a94-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it's beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="13a94-118">대리자를 호출 하면 임의의 코드를 실행 하 고 보안, 정확성 및 호환성에 영향을 미칠 수 있는 것을 이해 하는 ✔️.</span><span class="sxs-lookup"><span data-stu-id="13a94-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="13a94-119">*&copy;2005 부분, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="13a94-119">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="13a94-120">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="13a94-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="13a94-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13a94-121">See also</span></span>

- [<span data-ttu-id="13a94-122">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="13a94-122">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="13a94-123">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="13a94-123">Framework Design Guidelines</span></span>](index.md)
