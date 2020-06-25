---
title: '방법: 디자이너를 사용하여 그림 로드'
description: Windows Forms PictureBox 컨트롤을 사용 하 여 디자인 타임에 폼에 그림을 로드 하 고 표시 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325597"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="b4d11-103">방법: 디자이너를 사용하여 그림 로드(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b4d11-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="b4d11-104">Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용 하면 속성을 유효한 그림으로 설정 하 여 디자인 타임에 폼에서 그림을 로드 하 고 표시할 수 있습니다 <xref:System.Windows.Forms.PictureBox.Image%2A> .</span><span class="sxs-lookup"><span data-stu-id="b4d11-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="b4d11-105">다음 표에서는 허용 되는 파일 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="b4d11-106">유형</span><span class="sxs-lookup"><span data-stu-id="b4d11-106">Type</span></span>|<span data-ttu-id="b4d11-107">파일 이름 확장명</span><span class="sxs-lookup"><span data-stu-id="b4d11-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="b4d11-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="b4d11-108">Bitmap</span></span>|<span data-ttu-id="b4d11-109">.bmp</span><span class="sxs-lookup"><span data-stu-id="b4d11-109">.bmp</span></span>|
|<span data-ttu-id="b4d11-110">아이콘</span><span class="sxs-lookup"><span data-stu-id="b4d11-110">Icon</span></span>|<span data-ttu-id="b4d11-111">.ico</span><span class="sxs-lookup"><span data-stu-id="b4d11-111">.ico</span></span>|
|<span data-ttu-id="b4d11-112">GIF</span><span class="sxs-lookup"><span data-stu-id="b4d11-112">GIF</span></span>|<span data-ttu-id="b4d11-113">.gif</span><span class="sxs-lookup"><span data-stu-id="b4d11-113">.gif</span></span>|
|<span data-ttu-id="b4d11-114">Emf</span><span class="sxs-lookup"><span data-stu-id="b4d11-114">Metafile</span></span>|<span data-ttu-id="b4d11-115">.wmf</span><span class="sxs-lookup"><span data-stu-id="b4d11-115">.wmf</span></span>|
|<span data-ttu-id="b4d11-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="b4d11-116">JPEG</span></span>|<span data-ttu-id="b4d11-117">.jpg</span><span class="sxs-lookup"><span data-stu-id="b4d11-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="b4d11-118">디자인 타임에 그림을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="b4d11-118">To display a picture at design time</span></span>

1. <span data-ttu-id="b4d11-119"><xref:System.Windows.Forms.PictureBox>폼에 컨트롤을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="b4d11-120">**속성** 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택 하 고 줄임표 단추를 선택 하 여 **열기** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="b4d11-121">특정 파일 형식 (예: .gif 파일)을 찾고 있는 경우 **파일 형식** 상자에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="b4d11-122">표시 하려는 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="b4d11-123">디자인 타임에 그림을 지우려면</span><span class="sxs-lookup"><span data-stu-id="b4d11-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="b4d11-124">**속성** 창에서 속성을 선택 <xref:System.Windows.Forms.PictureBox.Image%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="b4d11-125">이미지 개체 이름 왼쪽에 표시 되는 작은 축소판 이미지를 마우스 오른쪽 단추로 클릭 한 다음 **다시 설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d11-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4d11-126">참조</span><span class="sxs-lookup"><span data-stu-id="b4d11-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="b4d11-127">PictureBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="b4d11-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="b4d11-128">방법: 런타임에 그림의 크기 또는 위치 수정</span><span class="sxs-lookup"><span data-stu-id="b4d11-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="b4d11-129">방법: 런타임에 그림 설정</span><span class="sxs-lookup"><span data-stu-id="b4d11-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="b4d11-130">PictureBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b4d11-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
