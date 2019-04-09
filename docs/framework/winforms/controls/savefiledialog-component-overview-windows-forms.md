---
title: SaveFileDialog 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: b06c4d510cefdc7558944995594fd209b6121cb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103046"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="d0336-102">SaveFileDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d0336-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d0336-103">Windows Forms <xref:System.Windows.Forms.SaveFileDialog> 구성 요소는 미리 구성된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="d0336-104">표준으로 동일 **파일 저장** Windows에서 사용 하는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="d0336-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="d0336-105"><xref:System.Windows.Forms.CommonDialog> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="d0336-106">SaveFileDialog 구성 요소를 사용 하 여 작업</span><span class="sxs-lookup"><span data-stu-id="d0336-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="d0336-107">사용자가 직접 대화 상자를 구성 하는 대신 파일을 저장할 수 있도록 간단한 솔루션으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="d0336-108">표준 Windows 대화 상자에 의존 하 여 만든 응용 프로그램의 기본 기능을 사용자에 게 친숙 한 경우</span><span class="sxs-lookup"><span data-stu-id="d0336-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="d0336-109">그러나 때 사용 하는 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용자 고유의 파일 저장 논리를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="d0336-110">사용할 수는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 런타임에 대화 상자를 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="d0336-111">사용 하 여 읽기/쓰기 모드에서 파일을 열 수는 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0336-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="d0336-112">폼에 추가 될 때를 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소가 Windows Forms 디자이너 아래쪽에 있는 트레이에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d0336-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0336-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0336-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="d0336-114">SaveFileDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d0336-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
