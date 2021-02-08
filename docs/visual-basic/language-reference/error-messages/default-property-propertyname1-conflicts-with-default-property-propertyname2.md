---
description: "자세한 정보: BC40007: 기본 속성 ' '이 ( <propertyname1> 가) ' '의 기본 속성 ' '과 (와) 충돌 <propertyname2> <classname> 하므로 ' Shadows '로 선언 되어야 합니다."
title: 기본 속성 '<propertyname1>'은(는) '<propertyname2>'의 기본 속성 '<classname>'과(와) 충돌하므로 'Shadows'로 선언해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 8ec7e36da18bbf8dda35e1a521d64268d14b7b26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796641"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="d3304-103">BC40007: ' '의 기본 속성 ' '이 ( \<propertyname1> 가) ' '의 기본 속성 ' '과 (와) 충돌 \<propertyname2> \<classname> 하므로 ' s h a r '로 선언</span><span class="sxs-lookup"><span data-stu-id="d3304-103">BC40007: Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>

<span data-ttu-id="d3304-104">속성이 기본 클래스에 정의 된 속성과 같은 이름으로 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3304-104">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="d3304-105">이 경우이 클래스의 속성은 기본 클래스 속성을 숨겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3304-105">In this situation, the property in this class should shadow the base class property.</span></span>

 <span data-ttu-id="d3304-106">이 메시지는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d3304-106">This message is a warning.</span></span> <span data-ttu-id="d3304-107">기본적으로`Shadows` 로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3304-107">`Shadows` is assumed by default.</span></span> <span data-ttu-id="d3304-108">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3304-108">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="d3304-109">**오류 ID:** BC40007</span><span class="sxs-lookup"><span data-stu-id="d3304-109">**Error ID:** BC40007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d3304-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d3304-110">To correct this error</span></span>

- <span data-ttu-id="d3304-111">키워드를 `Shadows` 선언에 추가 하거나 선언 되는 속성의 이름을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3304-111">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3304-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3304-112">See also</span></span>

- [<span data-ttu-id="d3304-113">Overloads</span><span class="sxs-lookup"><span data-stu-id="d3304-113">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="d3304-114">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="d3304-114">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
