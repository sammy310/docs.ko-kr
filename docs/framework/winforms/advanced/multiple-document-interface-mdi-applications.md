---
title: MDI 애플리케이션
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717449"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="019bf-102">MDI 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="019bf-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="019bf-103">(MDI) 다중 문서 인터페이스 응용 프로그램을 사용 하면 별도 창에 표시 된 각 문서를 사용 하 여 동시에 여러 문서를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="019bf-104">MDI 응용 프로그램 창 메뉴 항목과 창 또는 문서를 전환할 수 있는 하위 메뉴가 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="019bf-105">Windows Forms에서 단일 문서 인터페이스 (SDI) windows MDI 폼 사이의 몇 가지 동작 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="019bf-106">`Opacity` 속성 MDI 자식 폼의 모양에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="019bf-107">또한는 <xref:System.Windows.Forms.Form.CenterToParent%2A> 메서드 MDI 자식 폼의 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="019bf-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="019bf-108">In This Section</span></span>  
 [<span data-ttu-id="019bf-109">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="019bf-109">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="019bf-110">MDI 응용 프로그램 내에서 여러 문서에 대 한 컨테이너를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="019bf-111">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="019bf-111">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="019bf-112">MDI 부모 폼 내에서 작동 하는 하나 이상의 창 만들기에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="019bf-113">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="019bf-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="019bf-114">포커스가 있는 자식 창을 확인 하는 방법을 설명 (및 해당 내용을 클립보드에 보내는).</span><span class="sxs-lookup"><span data-stu-id="019bf-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="019bf-115">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="019bf-115">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="019bf-116">활성 자식 창에 대 한 정보를 전송 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="019bf-117">방법: MDI 자식 폼 정렬</span><span class="sxs-lookup"><span data-stu-id="019bf-117">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="019bf-118">바둑판식 배열, 계단식 또는 자식 창을 MDI 응용 프로그램의 정렬에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="019bf-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>
