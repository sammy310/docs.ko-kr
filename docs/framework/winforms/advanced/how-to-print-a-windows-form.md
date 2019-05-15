---
title: '방법: Windows Form 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: cd10e0a43ff37b921dc8e024d7a6a51fafbb0400
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591858"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="ed3a8-102">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="ed3a8-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="ed3a8-103">개발 프로세스의 일환으로, 일반적으로 하려는 Windows Form의 복사본을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="ed3a8-104">다음 코드 예제를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed3a8-105">예제</span><span class="sxs-lookup"><span data-stu-id="ed3a8-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ed3a8-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ed3a8-106">Robust Programming</span></span>  
 <span data-ttu-id="ed3a8-107">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-107">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ed3a8-108">프린터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-108">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="ed3a8-109">설치 된 프린터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-109">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ed3a8-110">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ed3a8-110">.NET Framework Security</span></span>  
 <span data-ttu-id="ed3a8-111">이 코드 예제를 실행 하기 위해 사용할 프린터를 사용 하 여 컴퓨터를 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-111">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3a8-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed3a8-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="ed3a8-113">방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed3a8-113">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="ed3a8-114">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="ed3a8-114">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
