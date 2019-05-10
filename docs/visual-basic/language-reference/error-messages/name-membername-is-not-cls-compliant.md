---
title: 이름 <membername>은(는) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 2d89d3588b854c9e77445a9980530d8dd53c33c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592009"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="8cfbd-102">이름 \<membername > CLS 규격이 아님</span><span class="sxs-lookup"><span data-stu-id="8cfbd-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="8cfbd-103">로 표시 되어 어셈블리로 `<CLSCompliant(True)>` 밑줄로 시작 하는 이름 가진 멤버를 노출 하지만 (`_`).</span><span class="sxs-lookup"><span data-stu-id="8cfbd-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="8cfbd-104">프로그래밍 요소를 호환 되어야 하지만 하나 이상의 밑줄을 포함할 수 있습니다 합니다 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="8cfbd-105">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="8cfbd-106"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="8cfbd-107">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="8cfbd-108">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="8cfbd-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-109">By default, this message is a warning.</span></span> <span data-ttu-id="8cfbd-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8cfbd-111">**오류 ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="8cfbd-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8cfbd-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8cfbd-112">To correct this error</span></span>  
  
- <span data-ttu-id="8cfbd-113">소스 코드를 제어할 경우 멤버 이름을 밑줄로 시작 하지 않도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="8cfbd-114">멤버 이름을 그대로 유지 하는, 필요한 경우 제거 합니다 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="8cfbd-115">어셈블리를 여전히 표시할 수 있습니다 `<CLSCompliant(True)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cfbd-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfbd-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cfbd-116">See also</span></span>

- [<span data-ttu-id="8cfbd-117">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="8cfbd-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="8cfbd-118">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="8cfbd-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
