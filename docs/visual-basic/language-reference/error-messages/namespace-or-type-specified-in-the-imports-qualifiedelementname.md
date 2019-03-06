---
title: Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 1873c0af7a251afd7754557f5dcb6aed13eb9f11
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357887"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="42afe-102">Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="42afe-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="42afe-103">Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="42afe-104">네임 스페이스 또는 형식 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="42afe-105">별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42afe-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="42afe-106">`Imports` 문에서 지정을 포함 하는 요소를 찾을 수 없습니다를 정의 하지 않습니다 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="42afe-107">A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="42afe-108">요소를 포함 하는 변수, 프로시저 또는 다른 요소를 포함 하는 등의 멤버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="42afe-109">가져오기의 목적은 이러한를 한정할 필요 없이 네임 스페이스 또는 형식 멤버에 액세스 하기 위해 코드를 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="42afe-110">프로젝트 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="42afe-111">자세한 내용은 "를 포함 하는 요소 가져오기"를 참조 하세요 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="42afe-112">컴파일러는 포함 하는 지정 된 요소를 찾을 수 없으면 사용 하는 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="42afe-113">요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버 다음 참조가 없는 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="42afe-114">두 경우 모두에서 요소를 가져오는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="42afe-115">포함 하는 요소를 가져오고 가져오기 별칭을 할당 하는 경우 다음 사용할 수 없다는 가져오기 별칭에는 다른 요소를 가져오는 것을 염두에 두십시오.</span><span class="sxs-lookup"><span data-stu-id="42afe-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="42afe-116">다음 코드는 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="42afe-117">**오류 ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="42afe-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="42afe-118">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="42afe-118">To correct this error</span></span>

1. <span data-ttu-id="42afe-119">포함 하는 요소를 프로젝트에서 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="42afe-120">사양의 요소를 포함 하는 다른 가져오기의 모든 가져오기 별칭에 포함 되지 않습니다 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="42afe-121">포함 하는 요소가 하나 이상 노출 확인 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="42afe-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="42afe-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="42afe-122">See also</span></span>

- [<span data-ttu-id="42afe-123">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="42afe-123">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="42afe-124">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="42afe-124">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="42afe-125">공용</span><span class="sxs-lookup"><span data-stu-id="42afe-125">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="42afe-126">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="42afe-126">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="42afe-127">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="42afe-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
