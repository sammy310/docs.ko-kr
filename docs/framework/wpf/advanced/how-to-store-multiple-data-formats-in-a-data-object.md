---
title: '방법: 데이터 개체에 여러 데이터 형식 저장'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 3f8e7233e1d28fec1f7dac114b04287aa3aff49f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085053"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a><span data-ttu-id="aab54-102">방법: 데이터 개체에 여러 데이터 형식 저장</span><span class="sxs-lookup"><span data-stu-id="aab54-102">How to: Store Multiple Data Formats in a Data Object</span></span>
<span data-ttu-id="aab54-103">다음 예제에서는 사용 하는 방법의 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 여러 형식의 데이터 개체에 데이터를 추가 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="aab54-103">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aab54-104">예제</span><span class="sxs-lookup"><span data-stu-id="aab54-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aab54-105">설명</span><span class="sxs-lookup"><span data-stu-id="aab54-105">Description</span></span>  
  
### <a name="code"></a><span data-ttu-id="aab54-106">코드</span><span class="sxs-lookup"><span data-stu-id="aab54-106">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a><span data-ttu-id="aab54-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="aab54-107">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="aab54-108">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="aab54-108">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
