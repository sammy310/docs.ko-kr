---
description: "BC40056: Imports ' '에 지정 된 네임 스페이스 또는 형식에 <qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없는 경우에 대해 자세히 알아보세요."
title: Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: e98ba70660823196e763300cd33ec1ba9a9db3b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795705"
---
# <a name="bc40056-namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="42c26-103">BC40056: Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-103">BC40056: Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="42c26-104">Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-104">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="42c26-105">네임 스페이스 또는 형식이 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-105">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="42c26-106">별칭 이름이 다른 별칭을 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-106">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="42c26-107">`Imports`문에서 찾을 수 없거나 멤버를 정의 하지 않는 포함 하는 요소를 지정 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="42c26-107">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="42c26-108">*포함 하는 요소* 는 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-108">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="42c26-109">포함 하는 요소에는 변수, 프로시저 또는 포함 하는 다른 요소와 같은 멤버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-109">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="42c26-110">가져오기의 목적은 코드에서 한정 하지 않고 네임 스페이스 또는 형식 멤버에 액세스할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-110">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="42c26-111">프로젝트에서 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-111">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="42c26-112">자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="42c26-112">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="42c26-113">컴파일러가 지정 된 포함 요소를 찾을 수 없는 경우 해당 요소를 사용 하는 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-113">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="42c26-114">요소를 찾았지만 요소가 멤버를 노출 하지 않는 경우에는 `Public` 참조가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-114">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="42c26-115">두 경우 모두 요소를 가져오는 것은 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-115">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="42c26-116">포함 하는 요소를 가져와서 가져오기 별칭을 할당 하는 경우 해당 가져오기 별칭을 사용 하 여 다른 요소를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-116">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="42c26-117">다음 코드는 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-117">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="42c26-118">**오류 ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="42c26-118">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="42c26-119">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="42c26-119">To correct this error</span></span>

1. <span data-ttu-id="42c26-120">포함 하는 요소가 프로젝트에서 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-120">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="42c26-121">포함 하는 요소의 사양이 다른 가져오기의 가져오기 별칭을 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42c26-121">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="42c26-122">포함 하는 요소가 하나 이상의 멤버를 노출 하는지 확인 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="42c26-122">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="42c26-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42c26-123">See also</span></span>

- [<span data-ttu-id="42c26-124">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="42c26-124">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="42c26-125">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="42c26-125">Namespace Statement</span></span>](../statements/namespace-statement.md)
- [<span data-ttu-id="42c26-126">공용</span><span class="sxs-lookup"><span data-stu-id="42c26-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="42c26-127">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="42c26-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="42c26-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="42c26-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
