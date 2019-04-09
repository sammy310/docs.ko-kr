---
title: '방법: 특정 데이터 형식의 데이터 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080022"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="07751-102">방법: 특정 데이터 형식의 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="07751-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="07751-103">다음 예제에서는 지정 된 형식으로 데이터 개체에서 데이터를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07751-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07751-104">예제</span><span class="sxs-lookup"><span data-stu-id="07751-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="07751-105">설명</span><span class="sxs-lookup"><span data-stu-id="07751-105">Description</span></span>  
 <span data-ttu-id="07751-106">다음 예제 코드를 사용 하는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 먼저 지정 된 데이터에 서식을 지정 하는 경우를 확인 하는 오버 로드를 사용할 수 있습니다 (기본적으로 또는 자동 전환 하 여) 지정된 된 형식의 사용 가능한 경우 예제를 사용 하 여 데이터를 검색 합니다 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드.</span><span class="sxs-lookup"><span data-stu-id="07751-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="07751-107">코드</span><span class="sxs-lookup"><span data-stu-id="07751-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="07751-108">예제</span><span class="sxs-lookup"><span data-stu-id="07751-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="07751-109">설명</span><span class="sxs-lookup"><span data-stu-id="07751-109">Description</span></span>  
 <span data-ttu-id="07751-110">다음 예제 코드를 사용 하는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 먼저 지정된 된 데이터 형식의 고유 하 게 사용할 수 있는지를 확인 하는 오버 로드 (자동 변환할 수 있는 데이터 형식 필터링 됨); 예제는 를사용하여데이터를검색지정된된형식의사용가능한경우<xref:System.Windows.DataObject.GetData%28System.String%29>메서드.</span><span class="sxs-lookup"><span data-stu-id="07751-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="07751-111">코드</span><span class="sxs-lookup"><span data-stu-id="07751-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="07751-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="07751-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="07751-113">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="07751-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
