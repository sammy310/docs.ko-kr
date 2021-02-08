---
description: '자세한 정보: BC40031: 이름이 <membername> CLS 규격이 아님'
title: 이름 <membername>은(는) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 7abc4aee8bb468b523e5bdd2ac13947d19c926bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795757"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a><span data-ttu-id="495f6-103">BC40031: 이름이 \<membername> CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-103">BC40031: Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="495f6-104">어셈블리가로 표시 되어 `<CLSCompliant(True)>` 있지만 이름이 밑줄 ()로 시작 하는 멤버를 노출 `_` 합니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-104">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>

 <span data-ttu-id="495f6-105">프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)를 준수 하려면 밑줄로 시작 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-105">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="495f6-106">[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="495f6-106">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

 <span data-ttu-id="495f6-107"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="495f6-108">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-108">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="495f6-109">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="495f6-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-110">By default, this message is a warning.</span></span> <span data-ttu-id="495f6-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="495f6-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="495f6-112">**오류 ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="495f6-112">**Error ID:** BC40031</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="495f6-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="495f6-113">To correct this error</span></span>

- <span data-ttu-id="495f6-114">소스 코드에 대 한 제어 권한이 있는 경우 밑줄로 시작 하지 않도록 멤버 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-114">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>

- <span data-ttu-id="495f6-115">멤버 이름이 변경 되지 않은 상태로 유지 되어야 하는 경우 해당 <xref:System.CLSCompliantAttribute> 정의에서를 제거 하거나로 표시 `<CLSCompliant(False)>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="495f6-115">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="495f6-116">여전히 어셈블리를로 표시할 수 있습니다 `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="495f6-116">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="495f6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="495f6-117">See also</span></span>

- [<span data-ttu-id="495f6-118">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="495f6-118">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="495f6-119">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="495f6-119">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
