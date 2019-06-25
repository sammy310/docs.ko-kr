---
title: '방법: 클립보드에 데이터 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 06ce64de5e2a6b4aa299b9ad9c41982b7c1924c7
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348270"
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="869a8-102">방법: 클립보드에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="869a8-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="869a8-103"><xref:System.Windows.Forms.Clipboard> 클래스는 Windows 운영 체제 클립보드 기능과 상호 작용 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="869a8-104">많은 응용 프로그램 데이터에 대 한 임시 저장소로 클립보드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="869a8-105">예를 들어 워드 프로세서 잘라내기 및 붙여넣기 작업 중 클립보드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="869a8-106">클립보드 다른 응용 프로그램에서 데이터를 전송할 때도 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="869a8-107">클립보드에 데이터를 추가 하면 해당 형식을 사용할 수 있으면 다른 응용 프로그램 데이터를 인식할 수 있도록 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="869a8-108">또한 데이터를 사용할 수 있도록 다른 응용 프로그램의 수를 늘리려면 다양 한 형식으로 클립보드에 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="869a8-109">클립보드 형식은 해당 형식을 사용 하는 응용 프로그램 관련된 데이터를 검색할 수 있도록 형식을 식별 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="869a8-110"><xref:System.Windows.Forms.DataFormats> 클래스 사용에 대 한 미리 정의 된 형식 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="869a8-111">사용자 고유의 형식 이름을 사용 하거나 해당 형식으로 개체의 형식을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="869a8-112">하나 이상의 형식으로 클립보드에 데이터를 추가 하려면 사용 된 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="869a8-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="869a8-113">이 메서드에 개체를 전달할 수 있습니다 하지만 여러 형식에 데이터를 추가 하려면 먼저 추가 해야 데이터를 별도 개체로 여러 형식으로 작동 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="869a8-114">일반적으로 데이터를 추가 합니다는 <xref:System.Windows.Forms.DataObject>를 구현 하는 모든 형식을 사용할 수 있지만 <xref:System.Windows.Forms.IDataObject> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="869a8-115">.NET Framework 2.0의 기본 클립보드 작업을 쉽게 수행할 수 있도록 설계 된 새 메서드를 사용 하 여 클립보드에 직접 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-115">In .NET Framework 2.0, you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="869a8-116">텍스트와 같은 단일의 공통 형식으로 데이터를 사용 하 여 작업할 때 이러한 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="869a8-117">모든 Windows 기반 응용 프로그램은 클립보드를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="869a8-118">따라서 내용이 변경 될 수 있습니다 다른 응용 프로그램으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="869a8-119"><xref:System.Windows.Forms.Clipboard> 단일 스레드 아파트 (STA) 모드를 설정 하는 스레드의 클래스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="869a8-120">이 클래스를 사용 하려면 프로그램 `Main` 표시 된 메서드가 <xref:System.STAThreadAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="869a8-121">개체를 클립보드에 배치할 수 있도록 serializable 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="869a8-122">직렬화 가능 형식 확인을 표시 하는 <xref:System.SerializableAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="869a8-123">클립보드 메서드에 순차 불가능 한 개체를 전달 하는 경우 메서드가 예외를 throw 하지 않고 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="869a8-124">serialization에 대한 자세한 내용은 <xref:System.Runtime.Serialization>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="869a8-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="869a8-125">단일의 공통 형식으로 클립보드에 데이터를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="869a8-125">To add data to the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="869a8-126">사용 된 <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, 또는 <xref:System.Windows.Forms.Clipboard.SetText%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="869a8-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="869a8-127">이러한 메서드는.NET Framework 2.0 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-127">These methods are available only in .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="869a8-128">사용자 지정 형식으로 클립보드에 데이터를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="869a8-128">To add data to the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="869a8-129">사용 하 여는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드를 사용자 지정 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="869a8-130">이 메서드는.NET Framework 2.0 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-130">This method is available only in .NET Framework 2.0.</span></span>  
  
     <span data-ttu-id="869a8-131">미리 정의 된 형식 이름을 사용 하 여 사용할 수도 있습니다는 <xref:System.Windows.Forms.Clipboard.SetData%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="869a8-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="869a8-132">자세한 내용은 <xref:System.Windows.Forms.DataFormats>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="869a8-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="869a8-133">여러 형식으로 클립보드에 데이터를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="869a8-133">To add data to the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="869a8-134">사용 된 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> 메서드와 전달을 <xref:System.Windows.Forms.DataObject> 데이터를 포함 하는.</span><span class="sxs-lookup"><span data-stu-id="869a8-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="869a8-135">.NET Framework 2.0 보다 이전 버전에서 클립보드에 데이터를 추가 하려면이 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="869a8-135">You must use this method to add data to the Clipboard on versions earlier than .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="869a8-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="869a8-136">See also</span></span>

- [<span data-ttu-id="869a8-137">끌어서 놓기 작업 및 클립보드 지원</span><span class="sxs-lookup"><span data-stu-id="869a8-137">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="869a8-138">방법: 클립보드에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="869a8-138">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
