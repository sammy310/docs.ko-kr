---
title: 프로젝트 수준의 Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 105fa8da838938d13022c210c1f65cdafd251003
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308486"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="bfdc6-102">프로젝트 수준의 Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="bfdc6-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="bfdc6-103">프로젝트 수준의 Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="bfdc6-104">네임 스페이스 또는 형식 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="bfdc6-105">별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="bfdc6-106">프로젝트 가져오기 속성을 포함 하는 요소를 찾을 수 없습니다를 정의 하지 않습니다 지정 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="bfdc6-107">A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="bfdc6-108">요소를 포함 하는 변수, 프로시저 또는 다른 요소를 포함 하는 등의 멤버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="bfdc6-109">가져오기의 목적은 이러한를 한정할 필요 없이 네임 스페이스 또는 형식 멤버에 액세스 하기 위해 코드를 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="bfdc6-110">프로젝트 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="bfdc6-111">자세한 내용은 "를 포함 하는 요소 가져오기"를 참조 하세요 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="bfdc6-112">컴파일러는 포함 하는 지정 된 요소를 찾을 수 없으면 사용 하는 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="bfdc6-113">요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버 다음 참조가 없는 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="bfdc6-114">두 경우 모두에서 요소를 가져오는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="bfdc6-115">사용할 합니다 **프로젝트 디자이너** 가져올 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="bfdc6-116">사용 합니다 **가져온 네임 스페이스** 섹션을 **참조** 페이지.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="bfdc6-117">가져올 수 있습니다는 **프로젝트 디자이너** 두 번 클릭 합니다 **My Project** 에서 아이콘 **솔루션 탐색기**.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="bfdc6-118">**오류 ID:** BC40057</span><span class="sxs-lookup"><span data-stu-id="bfdc6-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bfdc6-119">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bfdc6-119">To correct this error</span></span>  
  
1. <span data-ttu-id="bfdc6-120">열기는 **프로젝트 디자이너** 으로 전환 합니다 **참조** 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="bfdc6-121">에 **가져온 네임 스페이스** 섹션을 포함 하는 요소를 프로젝트에서 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="bfdc6-122">포함 하는 요소가 하나 이상 노출 확인 `Public` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdc6-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="bfdc6-123">See also</span></span>

- [<span data-ttu-id="bfdc6-124">참조 페이지, 프로젝트 디자이너(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfdc6-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="bfdc6-125">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="bfdc6-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="bfdc6-126">Public</span><span class="sxs-lookup"><span data-stu-id="bfdc6-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="bfdc6-127">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bfdc6-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="bfdc6-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="bfdc6-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
