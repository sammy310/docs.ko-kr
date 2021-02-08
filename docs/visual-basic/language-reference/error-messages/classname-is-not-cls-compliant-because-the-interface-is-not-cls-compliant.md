---
description: "BC40029: ' ' <classname> 인터페이스가 cls 규격이 아니므로이에 대 한 자세한 정보: ' '은 (는) cls 규격이 아닙니다. <interfacename>"
title: "'<classname>' 인터페이스가 CLS 규격이 아니므로 이 인터페이스에서 상속된 '<interfacename>'은(는) CLS 규격이 아닙니다."
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 28264dd602bd20a6b33bebd965982ca12d402d01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796772"
---
# <a name="bc40029-classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a><span data-ttu-id="5e005-103">BC40029: ' ' 인터페이스가 CLS 규격이 아니므로이 인터페이스에서 구현 하는 ' ' \<classname> 인터페이스가 cls 규격이 아닙니다. \<interfacename></span><span class="sxs-lookup"><span data-stu-id="5e005-103">BC40029: '\<classname>' is not CLS-compliant because the interface '\<interfacename>' it implements is not CLS-compliant</span></span>

<span data-ttu-id="5e005-104">클래스 또는 인터페이스가 `<CLSCompliant(True)>` 로 표시 또는 표시되지 않은 형식을 구현하거나 해당 형식에서 파생될 때 `<CLSCompliant(False)>` 로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-104">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="5e005-105">클래스 또는 인터페이스가 [언어 독립성 및 CLS (Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) )를 준수 하도록 하려면 전체 상속 계층이 규정을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-105">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="5e005-106">즉, 직접이든 간접이든 상속하는 모든 형식이 규격을 준수해야 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-106">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="5e005-107">마찬가지로 클래스가 하나 이상의 인터페이스를 구현하는 경우 해당 상속 계층 전체가 모두 규격을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-107">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>

 <span data-ttu-id="5e005-108"><xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5e005-109">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-109">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="5e005-110">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="5e005-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-111">By default, this message is a warning.</span></span> <span data-ttu-id="5e005-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e005-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="5e005-113">**오류 ID:** BC40029</span><span class="sxs-lookup"><span data-stu-id="5e005-113">**Error ID:** BC40029</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5e005-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5e005-114">To correct this error</span></span>

- <span data-ttu-id="5e005-115">CLS 규격이 필요하면 다른 상속 계층 구조에서 이 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-115">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>

- <span data-ttu-id="5e005-116">이 형식이 현재 상속 계층 구조 또는 구현 체계에 유지되어야 하는 경우 해당 정의에서 <xref:System.CLSCompliantAttribute> 를 제거하거나 `<CLSCompliant(False)>`로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5e005-116">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>
