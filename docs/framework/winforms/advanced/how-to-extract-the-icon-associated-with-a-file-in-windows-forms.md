---
title: '방법: Windows Forms에서 파일과 연결된 아이콘 추출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: d754dc5e8a57b3c4e2e5439bb2524a22d44813c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112556"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="5d2b5-102">방법: Windows Forms에서 파일과 연결된 아이콘 추출</span><span class="sxs-lookup"><span data-stu-id="5d2b5-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="5d2b5-103">여러 파일에는 시각적 연결된 된 파일 형식으로 제공 하는 아이콘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="5d2b5-104">예를 들어 Microsoft Word 문서를 Word 문서로 하 게 식별 하는 아이콘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="5d2b5-105">목록 컨트롤 또는 테이블 컨트롤에서 파일을 표시 하는 경우에 각 파일 이름 옆에 있는 파일 형식을 나타내는 아이콘을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="5d2b5-106">사용 하 여이 작업을 쉽게 수행할 수 있습니다는 <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d2b5-107">예제</span><span class="sxs-lookup"><span data-stu-id="5d2b5-107">Example</span></span>  
 <span data-ttu-id="5d2b5-108">다음 코드 예제에는 파일과 연결 된 아이콘 추출 파일 이름 및 연결 된 아이콘을 표시 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d2b5-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5d2b5-109">Compiling the Code</span></span>  
 <span data-ttu-id="5d2b5-110">예제를 컴파일하려면:</span><span class="sxs-lookup"><span data-stu-id="5d2b5-110">To compile the example:</span></span>  
  
-   <span data-ttu-id="5d2b5-111">Windows 폼 호출에 위의 코드를 붙여넣고 합니다 `ExtractAssociatedIconExample` 폼의 생성자에서 메서드 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="5d2b5-112">폼을 가져옵니다는 있는지 확인 해야 합니다 <xref:System.IO> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d2b5-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2b5-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d2b5-113">See also</span></span>

- [<span data-ttu-id="5d2b5-114">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="5d2b5-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="5d2b5-115">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5d2b5-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
