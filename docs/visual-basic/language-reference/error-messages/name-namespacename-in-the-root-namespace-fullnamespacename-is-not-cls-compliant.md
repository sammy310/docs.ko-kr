---
title: 루트 네임스페이스 <namespacename>의 이름 <fullnamespacename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 84706719d151ea8df478f88610df34842f6f8702
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918361"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="dc849-102">이름을 \<namespacename > 루트 네임 스페이스에서 \<fullnamespacename > CLS 규격이 아님</span><span class="sxs-lookup"><span data-stu-id="dc849-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="dc849-103">로 어셈블리 표시 됩니다 `<CLSCompliant(True)>`에 요소의 루트 네임 스페이스 이름 밑줄로 시작 하지만 (`_`).</span><span class="sxs-lookup"><span data-stu-id="dc849-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="dc849-104">프로그래밍 요소를 호환 되어야 하지만 하나 이상의 밑줄을 포함할 수 있습니다 합니다 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="dc849-105">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc849-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="dc849-106"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="dc849-107">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="dc849-108">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="dc849-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-109">By default, this message is a warning.</span></span> <span data-ttu-id="dc849-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc849-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dc849-111">**오류 ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="dc849-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc849-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="dc849-112">To correct this error</span></span>  
  
- <span data-ttu-id="dc849-113">CLS 규격에 필요한 경우 밑줄로 시작 하는 해당 요소 중 루트 네임 스페이스 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="dc849-114">네임 스페이스 이름을 그대로 유지 하는, 필요한 경우 다음 제거 합니다 <xref:System.CLSCompliantAttribute> 어셈블리에서로 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc849-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc849-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc849-115">See also</span></span>

- [<span data-ttu-id="dc849-116">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="dc849-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="dc849-117">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="dc849-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="dc849-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="dc849-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [<span data-ttu-id="dc849-119">프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc849-119">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="dc849-120">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="dc849-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="dc849-121">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="dc849-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
