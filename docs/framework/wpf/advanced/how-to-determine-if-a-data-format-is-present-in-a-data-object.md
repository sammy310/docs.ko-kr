---
title: '방법: 데이터 개체에 데이터 형식이 있는지 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 57190b94988c8ee557e99836a8e8500bfb622f2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379174"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="2b4d2-102">방법: 데이터 개체에 데이터 형식이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="2b4d2-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="2b4d2-103">다음 예제에서는 다양 한를 사용 하는 방법을 보여 줍니다 <xref:System.Windows.DataObject.GetDataPresent%2A> 특정 데이터 형식의 데이터 개체에 있는지 여부를 쿼리 메서드 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b4d2-104">예제</span><span class="sxs-lookup"><span data-stu-id="2b4d2-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b4d2-105">설명</span><span class="sxs-lookup"><span data-stu-id="2b4d2-105">Description</span></span>  
 <span data-ttu-id="2b4d2-106">다음 예제 코드를 사용 하는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 설명자 문자열에서 특정 데이터 형식의 존재에 대 한 쿼리를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b4d2-107">코드</span><span class="sxs-lookup"><span data-stu-id="2b4d2-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="2b4d2-108">예제</span><span class="sxs-lookup"><span data-stu-id="2b4d2-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b4d2-109">설명</span><span class="sxs-lookup"><span data-stu-id="2b4d2-109">Description</span></span>  
 <span data-ttu-id="2b4d2-110">다음 예제 코드를 사용 하는 <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> 형식에서 특정 데이터 형식의 존재에 대 한 쿼리를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b4d2-111">코드</span><span class="sxs-lookup"><span data-stu-id="2b4d2-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="2b4d2-112">예제</span><span class="sxs-lookup"><span data-stu-id="2b4d2-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b4d2-113">설명</span><span class="sxs-lookup"><span data-stu-id="2b4d2-113">Description</span></span>  
 <span data-ttu-id="2b4d2-114">다음 예제 코드를 사용 하는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 설명자 문자열을 데이터에 대 한 쿼리를 오버 로드 하 고 자동 변환할 수 있는 데이터 형식을 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4d2-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b4d2-115">코드</span><span class="sxs-lookup"><span data-stu-id="2b4d2-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="2b4d2-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b4d2-116">See also</span></span>
- <xref:System.Windows.IDataObject>
