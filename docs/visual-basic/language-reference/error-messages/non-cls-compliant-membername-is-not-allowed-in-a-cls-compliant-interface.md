---
title: CLS 규격 인터페이스에는 CLS 규격이 아닌 <membername>을(를) 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: dbffe2bd196e798b90104aebb74269387660c794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918205"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="22339-102">비-CLS 규격 \<membername > CLS 규격 인터페이스에 허용 되지 않습니다</span><span class="sxs-lookup"><span data-stu-id="22339-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="22339-103">속성, 프로시저 또는 인터페이스의 이벤트로 표시 됩니다 `<CLSCompliant(True)>` 인터페이스 자체으로 표시 되 면 `<CLSCompliant(False)>` 되거나 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22339-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="22339-104">호환 되어야 하는 인터페이스에 대 한 합니다 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS)와 모든 해당 멤버 규정을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22339-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="22339-105"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22339-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="22339-106">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22339-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="22339-107">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="22339-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="22339-108">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="22339-108">By default, this message is a warning.</span></span> <span data-ttu-id="22339-109">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22339-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="22339-110">**오류 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="22339-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22339-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="22339-111">To correct this error</span></span>  
  
- <span data-ttu-id="22339-112">CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어할 경우 표시 된 인터페이스로 `<CLSCompliant(True)>` 의 모든 멤버는 규정을 준수 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="22339-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
- <span data-ttu-id="22339-113">CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어할 수 없는 경우 또는 호환 되도록 맞지 않을 경우 다른 인터페이스 내에서이 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="22339-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
- <span data-ttu-id="22339-114">이 멤버는 현재 인터페이스 내에서 유지 하려면를 제거 합니다 <xref:System.CLSCompliantAttribute> 해당 정의에서 표시 하거나 `<CLSCompliant(False)>`합니다.</span><span class="sxs-lookup"><span data-stu-id="22339-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22339-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="22339-115">See also</span></span>

- [<span data-ttu-id="22339-116">Interface 문</span><span class="sxs-lookup"><span data-stu-id="22339-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
