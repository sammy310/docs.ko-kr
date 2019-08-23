---
title: 기본 폼의 모양 수정 효과
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: b24bd2db564c7acb0a748c47095ee0777ea1eb88
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955154"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="cdbeb-102">기본 폼의 모양 수정 효과</span><span class="sxs-lookup"><span data-stu-id="cdbeb-102">Effects of modifying a base form's appearance</span></span>

<span data-ttu-id="cdbeb-103">애플리케이션을 개발하는 동안 프로젝트(또는 다른 프로젝트)에 있는 다른 양식을 상속하는 기본 양식의 모양을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdbeb-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>

<span data-ttu-id="cdbeb-104">디자인 타임에서 기본 양식의 모양 변경(속성 설정 또는 컨트롤의 더하기와 빼기)은 기본 양식을 포함하는 프로젝트를 빌드할 때 상속된 양식에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdbeb-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="cdbeb-105">단순히 기본 양식에 대한 변경 내용을 저장하기에는 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdbeb-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="cdbeb-106">프로젝트를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdbeb-106">To build a project, choose **Build** from the **Build** menu.</span></span>

<span data-ttu-id="cdbeb-107">런타임 시 기본 양식에 대한 수정은 이미 인스턴스화된 상속된 양식에 아무 영향도 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdbeb-107">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdbeb-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdbeb-108">See also</span></span>

- [<span data-ttu-id="cdbeb-109">base</span><span class="sxs-lookup"><span data-stu-id="cdbeb-109">base</span></span>](../../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="cdbeb-110">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="cdbeb-110">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="cdbeb-111">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="cdbeb-111">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
