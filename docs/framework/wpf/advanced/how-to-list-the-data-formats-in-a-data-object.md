---
title: '방법: 데이터 개체의 데이터 형식 나열'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001496"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="b1de7-102">방법: 데이터 개체의 데이터 형식 나열</span><span class="sxs-lookup"><span data-stu-id="b1de7-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="b1de7-103">다음 예제에 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.DataObject.GetFormats%2A> 메서드 오버 로드 된 데이터 개체에서 사용할 수 있는 각 데이터 형식을 나타내는 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1de7-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1de7-104">예제</span><span class="sxs-lookup"><span data-stu-id="b1de7-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1de7-105">설명</span><span class="sxs-lookup"><span data-stu-id="b1de7-105">Description</span></span>  
 <span data-ttu-id="b1de7-106">다음 예제 코드를 사용 하 여 <xref:System.Windows.DataObject.GetFormats%2A> 오버 로드를 통해 데이터 개체 (네이티브 및 자동 변환 가능)에서 사용할 수 있는 모든 데이터 형식을 나타내는 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1de7-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1de7-107">코드</span><span class="sxs-lookup"><span data-stu-id="b1de7-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="b1de7-108">예제</span><span class="sxs-lookup"><span data-stu-id="b1de7-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1de7-109">설명</span><span class="sxs-lookup"><span data-stu-id="b1de7-109">Description</span></span>  
 <span data-ttu-id="b1de7-110">다음 예제 코드를 사용 하 여 <xref:System.Windows.DataObject.GetFormats%2A> 오버 로드를 데이터 개체 (자동 변환할 수 있는 데이터 형식 필터링 됨)에 사용할 수 있는 데이터 형식만 나타내는 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1de7-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1de7-111">코드</span><span class="sxs-lookup"><span data-stu-id="b1de7-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="b1de7-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1de7-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="b1de7-113">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="b1de7-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
