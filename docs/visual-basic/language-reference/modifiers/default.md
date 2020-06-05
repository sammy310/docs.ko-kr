---
title: 기본값
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 0c2808795d6fcbad7892369fd7f460ebf0406093
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372974"
---
# <a name="default-visual-basic"></a><span data-ttu-id="26ca5-102">Default(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26ca5-102">Default (Visual Basic)</span></span>
<span data-ttu-id="26ca5-103">속성을 해당 클래스, 구조체 또는 인터페이스의 기본 속성으로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26ca5-104">설명</span><span class="sxs-lookup"><span data-stu-id="26ca5-104">Remarks</span></span>  
 <span data-ttu-id="26ca5-105">클래스, 구조체 또는 인터페이스는 하나 이상의 매개 변수를 사용 하는 경우 해당 속성 중 하나를 *기본 속성*으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="26ca5-106">코드에서 멤버를 지정 하지 않고 클래스 또는 구조체에 대 한 참조를 만드는 경우 Visual Basic는 기본 속성에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="26ca5-107">기본 속성은 소스 코드 문자를 조금 줄일 수 있지만 코드를 읽기 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="26ca5-108">호출 코드가 클래스 또는 구조체를 사용 하는 데 익숙하지 않은 경우 클래스 또는 구조체 이름에 대 한 참조를 만들 때 참조가 클래스나 구조체 자체에 액세스 하는지 아니면 기본 속성에 액세스 하는지 여부를 확신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="26ca5-109">이로 인해 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="26ca5-110">항상 [Option Strict 문을](../statements/option-strict-statement.md) 사용 하 여 컴파일러 유형 검사를로 설정 하 여 기본 속성 오류의 가능성을 약간 줄일 수 있습니다 `On` .</span><span class="sxs-lookup"><span data-stu-id="26ca5-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="26ca5-111">코드에서 미리 정의 된 클래스 또는 구조체를 사용 하려는 경우 기본 속성이 있는지 여부를 확인 하 고, 해당 하는 경우 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="26ca5-112">이러한 단점 때문에 기본 속성을 정의 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="26ca5-113">코드 가독성을 위해 기본 속성도 항상 모든 속성을 명시적으로 참조 하는 것도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="26ca5-114">`Default`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ca5-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="26ca5-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="26ca5-115">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="26ca5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26ca5-116">See also</span></span>

- [<span data-ttu-id="26ca5-117">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="26ca5-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="26ca5-118">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="26ca5-118">Keywords</span></span>](../keywords/index.md)
