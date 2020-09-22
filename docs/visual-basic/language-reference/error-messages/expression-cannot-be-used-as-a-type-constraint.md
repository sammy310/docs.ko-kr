---
title: "'<expression>'은(는) 형식 제약 조건으로 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 4f1db6bdbe6f25d0362b55acd95e716fbc2417ed
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874274"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="8af36-102">'\<expression>'은(는) 형식 제약 조건으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-102">'\<expression>' cannot be used as a type constraint</span></span>

<span data-ttu-id="8af36-103">제약 조건 목록에 형식 매개 변수에 대한 유효한 제약 조건을 나타내지 않는 식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="8af36-104">제약 조건 목록은 형식 매개 변수에 전달되는 형식 인수에 대해 요구 사항을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="8af36-105">다음 요구 사항을 임의로 조합해서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-105">You can specify the following requirements in any combination:</span></span>  
  
- <span data-ttu-id="8af36-106">형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-106">The type argument must implement one or more interfaces</span></span>  
  
- <span data-ttu-id="8af36-107">형식 인수는 최대 하나의 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-107">The type argument must inherit from at most one class</span></span>  
  
- <span data-ttu-id="8af36-108">형식 인수는 만드는 코드가 액세스할 수 있는, 매개 변수 없는 생성자를 노출해야 합니다( `New` 제약 조건 포함).</span><span class="sxs-lookup"><span data-stu-id="8af36-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="8af36-109">제약 조건 목록에 특정 클래스 또는 인터페이스가 없는 경우 다음 중 하나를 지정하여 더 많은 일반 요구 사항을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
- <span data-ttu-id="8af36-110">형식 인수는 값 형식이어야 합니다( `Structure` 제약 조건 포함).</span><span class="sxs-lookup"><span data-stu-id="8af36-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
- <span data-ttu-id="8af36-111">형식 인수는 참조 형식이어야 합니다( `Class` 제약 조건 포함).</span><span class="sxs-lookup"><span data-stu-id="8af36-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="8af36-112">동일한 형식 매개 변수에 `Structure` 와 `Class` 를 둘 다 지정할 수 없으며 두 번 이상 지정할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="8af36-113">**오류 ID:** BC32061</span><span class="sxs-lookup"><span data-stu-id="8af36-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8af36-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8af36-114">To correct this error</span></span>  
  
- <span data-ttu-id="8af36-115">식과 해당 요소의 철자가 맞는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
- <span data-ttu-id="8af36-116">식이 앞의 요구 사항 목록에 맞지 않을 경우 제약 조건 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
- <span data-ttu-id="8af36-117">식이 인터페이스 또는 클래스를 참조하는 경우 컴파일러가 해당 인터페이스 또는 클래스에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="8af36-118">해당 이름을 한정하거나 프로젝트에 대한 참조를 추가해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af36-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="8af36-119">자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "프로젝트에 대 한 참조"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8af36-119">For more information, see "References to Projects" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af36-120">참조</span><span class="sxs-lookup"><span data-stu-id="8af36-120">See also</span></span>

- [<span data-ttu-id="8af36-121">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="8af36-121">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="8af36-122">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="8af36-122">Value Types and Reference Types</span></span>](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="8af36-123">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="8af36-123">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
