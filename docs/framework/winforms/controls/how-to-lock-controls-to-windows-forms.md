---
title: 컨트롤 잠그기
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736244"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="84dae-102">방법: 컨트롤을 Windows Forms로 잠그기</span><span class="sxs-lookup"><span data-stu-id="84dae-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="84dae-103">Windows 응용 프로그램의 UI (사용자 인터페이스)를 디자인할 때 컨트롤이 제대로 배치 되 면 컨트롤을 잠가 다른 속성을 설정할 때 실수로 이동 하거나 크기를 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="84dae-104">또한 폼의 모든 컨트롤을 한 번에 잠그거나 잠금 해제할 수 있습니다 .이는 많은 컨트롤이 있는 폼에 유용 하거나 개별 컨트롤의 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="84dae-105">폼에서 원하는 위치에 컨트롤을 모두 배치한 후에는 잘못 된 움직임을 방지 하기 위해 모든 컨트롤을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="84dae-106">컨트롤을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="84dae-106">To lock a control</span></span>

<span data-ttu-id="84dae-107">Visual Studio의 **속성** 창에서 **Locked** 속성을 선택 하 고 **true**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="84dae-108">(이름을 두 번 클릭 하면 속성 설정이 전환 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="84dae-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="84dae-109">또는 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 **컨트롤 잠금**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="84dae-110">컨트롤을 잠그면 디자인 화면의 새 크기 또는 위치로 끌어 올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="84dae-111">그러나 **속성** 창이 나 코드를 통해 컨트롤의 크기나 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="84dae-112">폼의 모든 컨트롤을 잠그려면</span><span class="sxs-lookup"><span data-stu-id="84dae-112">To lock all the controls on a form</span></span>

<span data-ttu-id="84dae-113">**서식** 메뉴에서 **컨트롤 잠금**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="84dae-114">이 명령은 폼이 컨트롤 이기 때문에 폼의 크기도 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="84dae-115">폼에서 잠긴 컨트롤의 잠금을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="84dae-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="84dae-116">**서식** 메뉴에서 **컨트롤 잠금**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="84dae-117">이제 폼에서 모든 이전에 잠긴 컨트롤의 잠금이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="84dae-118">개별적으로 잠긴 컨트롤의 잠금을 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="84dae-118">To unlock locked controls individually</span></span>

<span data-ttu-id="84dae-119">**속성** 창에서 **Locked** 속성을 선택 하 고 **false**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="84dae-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="84dae-120">(이름을 두 번 클릭 하면 속성 설정이 전환 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="84dae-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="84dae-121">참조</span><span class="sxs-lookup"><span data-stu-id="84dae-121">See also</span></span>

- [<span data-ttu-id="84dae-122">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="84dae-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="84dae-123">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="84dae-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="84dae-124">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="84dae-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="84dae-125">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="84dae-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
