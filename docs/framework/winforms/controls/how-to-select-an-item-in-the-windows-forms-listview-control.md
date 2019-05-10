---
title: '방법: Windows Forms ListView 컨트롤에서 항목 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 41a30ba6c242d0587e98b458e41ca213e8885bca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638199"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="35d73-102">방법: Windows Forms ListView 컨트롤에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="35d73-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="35d73-103">이 예제에서는 프로그래밍 방식으로 Windows Forms에서 항목을 선택 하는 방법에 설명 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d73-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="35d73-104">프로그래밍 방식으로 항목을 선택 하면 자동으로 바뀌지 않습니다에 포커스를 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d73-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="35d73-105">따라서 일반적으로 하려는 항목을 선택할 때 강조 하는 항목을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d73-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d73-106">예제</span><span class="sxs-lookup"><span data-stu-id="35d73-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35d73-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="35d73-107">Compiling the Code</span></span>  
 <span data-ttu-id="35d73-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="35d73-108">This example requires:</span></span>  
  
- <span data-ttu-id="35d73-109">A <xref:System.Windows.Forms.ListView> 제어 라는 `listView1` 하나 이상의 항목이 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d73-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="35d73-110"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="35d73-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d73-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="35d73-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
