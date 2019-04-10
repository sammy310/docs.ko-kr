---
title: 활동 클래스를 사용하여 워크플로 활동 제작
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322318"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="b6544-102">활동 클래스를 사용하여 워크플로 활동 제작</span><span class="sxs-lookup"><span data-stu-id="b6544-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="b6544-103">Windows WF (Workflow Foundation)에서 사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 에서 상속 되는 클래스를 만듭니다 <xref:System.Activities.Activity> 만들어지는 기능 조합 하 여 사용자 지정 활동 또는 활동에서의 [기본 제공 활동 라이브러리](net-framework-4-5-built-in-activity-library.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="b6544-104">이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="b6544-105">활동 디자이너를 사용하여 사용자 지정 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b6544-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="b6544-106">Visual Studio 2012를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="b6544-107">파일, 새로 만들기, 프로젝트를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-107">Select File, New, Project.</span></span> <span data-ttu-id="b6544-108">선택 **Workflow 4.0** 아래에서 **Visual C#** 에 **프로젝트 형식** 창에서 선택한 합니다 **v2010** 노드.</span><span class="sxs-lookup"><span data-stu-id="b6544-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="b6544-109">선택 **활동 라이브러리** 에 **템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="b6544-110">새 프로젝트의 이름을 HelloActivity로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="b6544-111">새 활동을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-111">Open the new activity.</span></span>  <span data-ttu-id="b6544-112">도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="b6544-113"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="b6544-114">입력 `"Hello World"` (따옴표로)에 **텍스트** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="b6544-115">두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="b6544-116">입력 `"Goodbye"` (따옴표로)에 **텍스트** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b6544-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
