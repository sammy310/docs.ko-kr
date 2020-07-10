---
title: MDI(다중 문서 인터페이스) 애플리케이션
description: MDI (다중 문서 인터페이스) 응용 프로그램을 사용 하 여 각 문서를 자체 창에 표시 하는 여러 문서를 동시에 표시 하 Windows Forms는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174655"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="6803d-103">MDI(다중 문서 인터페이스) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6803d-103">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="6803d-104">MDI (다중 문서 인터페이스) 응용 프로그램을 사용 하면 여러 문서를 동시에 표시할 수 있으며 각 문서는 자체 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-104">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="6803d-105">MDI 응용 프로그램에는 종종 창이 나 문서 간을 전환 하기 위한 하위 메뉴가 포함 된 창 메뉴 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-105">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6803d-106">Windows Forms의 MDI 폼과 SDI (단일 문서 인터페이스) 창 간에는 몇 가지 동작 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-106">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="6803d-107">`Opacity`속성은 MDI 자식 폼의 모양에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-107">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="6803d-108">또한이 <xref:System.Windows.Forms.Form.CenterToParent%2A> 메서드는 MDI 자식 폼의 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-108">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6803d-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6803d-109">In This Section</span></span>  
 [<span data-ttu-id="6803d-110">방법: MDI 부모 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="6803d-110">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="6803d-111">MDI 응용 프로그램 내에서 여러 문서에 대 한 컨테이너를 만들기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-111">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="6803d-112">방법: MDI 자식 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="6803d-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="6803d-113">MDI 부모 폼 내에서 작동 하는 하나 이상의 창을 만드는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-113">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="6803d-114">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="6803d-114">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="6803d-115">포커스가 있는 자식 창을 확인 하 고 해당 콘텐츠를 클립보드로 보내는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-115">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="6803d-116">방법: 활성 MDI 자식으로 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="6803d-116">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="6803d-117">활성 자식 창으로 정보를 전송 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-117">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="6803d-118">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="6803d-118">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="6803d-119">MDI 응용 프로그램의 자식 창에 대 한 바둑판식 배열, 계단식 배열 또는 정렬에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6803d-119">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
