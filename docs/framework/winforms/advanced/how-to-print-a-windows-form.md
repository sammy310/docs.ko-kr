---
title: '방법: Windows Form 인쇄'
description: CopyFromScreen 메서드를 사용 하 여 프로그래밍 방식으로 현재 Windows Form의 복사본을 인쇄 하는 방법을 알아봅니다.
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
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174694"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="3c4c8-103">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="3c4c8-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="3c4c8-104">개발 프로세스의 일부로, 일반적으로 Windows Form의 복사본을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4c8-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="3c4c8-105">다음 코드 예제에서는 메서드를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다 <xref:System.Drawing.Graphics.CopyFromScreen%2A> .</span><span class="sxs-lookup"><span data-stu-id="3c4c8-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c4c8-106">예제</span><span class="sxs-lookup"><span data-stu-id="3c4c8-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3c4c8-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3c4c8-107">Robust Programming</span></span>  
 <span data-ttu-id="3c4c8-108">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4c8-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="3c4c8-109">프린터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4c8-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="3c4c8-110">설치 된 프린터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4c8-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3c4c8-111">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="3c4c8-111">.NET Framework Security</span></span>  
 <span data-ttu-id="3c4c8-112">이 코드 예제를 실행 하려면 컴퓨터에서 사용 하는 프린터에 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4c8-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4c8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c4c8-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="3c4c8-114">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="3c4c8-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="3c4c8-115">방법: Windows Forms에서 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="3c4c8-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
