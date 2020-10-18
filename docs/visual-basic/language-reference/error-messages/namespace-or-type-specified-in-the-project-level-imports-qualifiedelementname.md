---
title: 프로젝트 수준의 Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 54ee046cda998be8bd70e531918d6ab2a67d0494
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160121"
---
# <a name="bc40057-namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="ac7f0-102">BC40057: 프로젝트 수준의 Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-102">BC40057: Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="ac7f0-103">프로젝트 수준의 Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="ac7f0-104">네임 스페이스 또는 형식이 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="ac7f0-105">별칭 이름이 다른 별칭을 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-105">Make sure the alias name doesn't contain other aliases.</span></span>

 <span data-ttu-id="ac7f0-106">프로젝트의 가져오기 속성은 찾을 수 없거나 멤버를 정의 하지 않는 포함 하는 요소를 지정 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="ac7f0-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

 <span data-ttu-id="ac7f0-107">*포함 하는 요소* 는 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="ac7f0-108">포함 하는 요소에는 변수, 프로시저 또는 포함 하는 다른 요소와 같은 멤버가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

 <span data-ttu-id="ac7f0-109">가져오기의 목적은 코드에서 한정 하지 않고 네임 스페이스 또는 형식 멤버에 액세스할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="ac7f0-110">프로젝트에서 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="ac7f0-111">자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

 <span data-ttu-id="ac7f0-112">컴파일러가 지정 된 포함 요소를 찾을 수 없는 경우 해당 요소를 사용 하는 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="ac7f0-113">요소를 찾았지만 요소가 멤버를 노출 하지 않는 경우에는 `Public` 참조가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="ac7f0-114">두 경우 모두 요소를 가져오는 것은 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-114">In either case it is meaningless to import the element.</span></span>

 <span data-ttu-id="ac7f0-115">**프로젝트 디자이너** 를 사용 하 여 가져올 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="ac7f0-116">**참조** 페이지의 **가져온 네임 스페이스** 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="ac7f0-117">**솔루션 탐색기**에서 **내 프로젝트** 아이콘을 두 번 클릭 하 여 **프로젝트 디자이너** 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>

 <span data-ttu-id="ac7f0-118">**오류 ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="ac7f0-118">**Error ID:** BC40057</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ac7f0-119">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ac7f0-119">To correct this error</span></span>

1. <span data-ttu-id="ac7f0-120">**프로젝트 디자이너** 를 열고 **참조** 페이지로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>

2. <span data-ttu-id="ac7f0-121">**가져온 네임 스페이스** 섹션에서 포함 하는 요소를 프로젝트에서 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac7f0-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>

3. <span data-ttu-id="ac7f0-122">포함 하는 요소가 하나 이상의 멤버를 노출 하는지 확인 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="ac7f0-122">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac7f0-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac7f0-123">See also</span></span>

- [<span data-ttu-id="ac7f0-124">참조 페이지, 프로젝트 디자이너(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac7f0-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="ac7f0-125">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="ac7f0-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="ac7f0-126">공용</span><span class="sxs-lookup"><span data-stu-id="ac7f0-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="ac7f0-127">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ac7f0-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="ac7f0-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="ac7f0-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
