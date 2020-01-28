---
title: '방법: 파일과 연결 된 아이콘 추출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742546"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="ab715-102">방법: Windows Forms에서 파일과 연결된 아이콘 추출</span><span class="sxs-lookup"><span data-stu-id="ab715-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="ab715-103">많은 파일에는 연결 된 파일 형식에 대 한 시각적 표현을 제공 하는 아이콘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="ab715-104">예를 들어 Microsoft Word 문서에는 Word 문서로 식별 하는 아이콘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="ab715-105">목록 컨트롤이 나 테이블 컨트롤에 파일을 표시 하는 경우 각 파일 이름 옆에 있는 파일 형식을 나타내는 아이콘을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="ab715-106"><xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드를 사용 하 여이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab715-107">예</span><span class="sxs-lookup"><span data-stu-id="ab715-107">Example</span></span>  
 <span data-ttu-id="ab715-108">다음 코드 예제에서는 파일에 연결 된 아이콘을 추출 하 고 <xref:System.Windows.Forms.ListView> 컨트롤에 파일 이름 및 연결 된 아이콘을 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab715-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ab715-109">Compiling the Code</span></span>  
 <span data-ttu-id="ab715-110">예제를 컴파일하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-110">To compile the example:</span></span>  
  
- <span data-ttu-id="ab715-111">위의 코드를 Windows Form에 붙여넣고 폼의 생성자 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드에서 `ExtractAssociatedIconExample` 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="ab715-112">양식이 <xref:System.IO> 네임 스페이스를 가져오는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab715-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab715-113">참조</span><span class="sxs-lookup"><span data-stu-id="ab715-113">See also</span></span>

- [<span data-ttu-id="ab715-114">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="ab715-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ab715-115">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ab715-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
