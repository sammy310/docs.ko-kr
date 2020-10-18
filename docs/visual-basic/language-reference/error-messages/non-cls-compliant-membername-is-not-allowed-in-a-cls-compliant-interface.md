---
title: CLS 규격 인터페이스에는 CLS 규격이 아닌 <membername>을(를) 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: aa7944e90857436553435ce783c0820770496a49
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159991"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="01ed1-102">BC40033: cls \<membername> 규격 인터페이스에는 cls 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-102">BC40033: Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>

<span data-ttu-id="01ed1-103">인터페이스의 속성, 프로시저 또는 이벤트는 `<CLSCompliant(True)>` 인터페이스 자체가로 표시 `<CLSCompliant(False)>` 되거나 표시 되지 않는 경우로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="01ed1-104">인터페이스가 [언어 독립성 및 CLS (Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) )를 준수 하 게 하려면 모든 멤버가 규격 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>

 <span data-ttu-id="01ed1-105"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="01ed1-106">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-106">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="01ed1-107">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="01ed1-108">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-108">By default, this message is a warning.</span></span> <span data-ttu-id="01ed1-109">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01ed1-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="01ed1-110">**오류 ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="01ed1-110">**Error ID:** BC40033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="01ed1-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="01ed1-111">To correct this error</span></span>

- <span data-ttu-id="01ed1-112">CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어 해야 하는 경우 인터페이스를 `<CLSCompliant(True)>` 모든 멤버가 규정을 준수 하는 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>

- <span data-ttu-id="01ed1-113">CLS 규격이 필요 하 고 인터페이스 소스 코드를 제어할 수 없는 경우 또는 규격이 아닌 경우 다른 인터페이스 내에서이 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>

- <span data-ttu-id="01ed1-114">이 멤버를 현재 인터페이스 내에 유지 해야 하는 경우 해당 <xref:System.CLSCompliantAttribute> 정의에서를 제거 하거나로 표시 `<CLSCompliant(False)>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="01ed1-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="01ed1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01ed1-115">See also</span></span>

- [<span data-ttu-id="01ed1-116">Interface 문</span><span class="sxs-lookup"><span data-stu-id="01ed1-116">Interface Statement</span></span>](../statements/interface-statement.md)
