---
title: '방법: 클립보드에서 데이터 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: e29e71974abda3e6e57d22d9faef28e386ebeefd
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169897"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="92d78-102">방법: 클립보드에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="92d78-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="92d78-103"><xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제 클립보드 기능과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="92d78-104">많은 응용 프로그램 데이터에 대 한 임시 저장소로 클립보드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="92d78-105">예를 들어 워드 프로세서 잘라내기 및 붙여넣기 작업 중 클립보드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="92d78-106">클립보드 다른 응용 프로그램에서 정보를 전송할 때도 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="92d78-107">일부 응용 프로그램 데이터를 사용할 수 있도록 다른 응용 프로그램의 수를 늘리려면 여러 형식으로 클립보드에 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="92d78-108">클립보드 형식은 형식을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="92d78-109">식별 된 형식을 사용 하는 응용 프로그램은 클립보드에 연결 된 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="92d78-110"><xref:System.Windows.Forms.DataFormats> 클래스 사용에 대 한 미리 정의 된 형식 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="92d78-111">사용자 고유의 형식 이름을 사용 하거나 해당 형식으로 개체의 형식을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="92d78-112">클립보드에 데이터를 추가 하는 방법에 대 한 내용은 [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="92d78-113">클립보드 데이터를 특정 형식으로 포함 되는지 여부를 확인 하려면 중 하나를 사용 합니다 `Contains` *형식을* 메서드 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92d78-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="92d78-114">클립보드에서 데이터를 검색할 중 하나를 사용 합니다 `Get` *형식을* 메서드 또는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92d78-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="92d78-115">이러한 메서드는.NET Framework 2.0의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-115">These methods are new in .NET Framework 2.0.</span></span>  
  
 <span data-ttu-id="92d78-116">버전을 사용 하 여 클립보드의 데이터에 액세스 하려면 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]를 사용 합니다 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드 반환 된 메서드를 호출 <xref:System.Windows.Forms.IDataObject>.</span><span class="sxs-lookup"><span data-stu-id="92d78-116">To access data from the Clipboard by using versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="92d78-117">특정 형식으로 반환된 된 개체의 사용 가능한 지 알아보려면, 예를 들어 호출 된 <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92d78-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92d78-118">모든 Windows 기반 응용 프로그램은 시스템 클립보드를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="92d78-119">따라서 내용이 변경 될 수 있습니다 다른 응용 프로그램으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="92d78-120"><xref:System.Windows.Forms.Clipboard> 단일 스레드 아파트 (STA) 모드를 설정 하는 스레드의 클래스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="92d78-121">이 클래스를 사용 하려면 프로그램 `Main` 표시 된 메서드가 <xref:System.STAThreadAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="92d78-122">단일의 공통 형식으로 클립보드의 데이터를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="92d78-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="92d78-123">사용 된 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, 또는 <xref:System.Windows.Forms.Clipboard.GetText%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92d78-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="92d78-124">필요에 따라 해당를 사용할 `Contains` *형식* 방법 먼저 데이터를 특정 형식으로 사용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="92d78-125">이러한 메서드는.NET Framework 2.0 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-125">These methods are available only in .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="92d78-126">사용자 지정 형식으로 클립보드의 데이터를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="92d78-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="92d78-127">사용 하 여는 <xref:System.Windows.Forms.Clipboard.GetData%2A> 메서드를 사용자 지정 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="92d78-128">이 메서드는.NET Framework 2.0 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-128">This method is available only in .NET Framework 2.0.</span></span>  
  
     <span data-ttu-id="92d78-129">미리 정의 된 형식 이름을 사용 하 여 사용할 수도 있습니다는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="92d78-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="92d78-130">자세한 내용은 <xref:System.Windows.Forms.DataFormats>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92d78-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="92d78-131">여러 형식으로 클립보드의 데이터를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="92d78-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="92d78-132"><xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="92d78-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="92d78-133">버전에서 클립보드의 데이터를 검색 하려면이 메서드를 사용 해야 이전의 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92d78-133">You must use this method to retrieve data from the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="92d78-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="92d78-134">See also</span></span>

- [<span data-ttu-id="92d78-135">끌어서 놓기 작업 및 클립보드 지원</span><span class="sxs-lookup"><span data-stu-id="92d78-135">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="92d78-136">방법: 클립보드에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="92d78-136">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
