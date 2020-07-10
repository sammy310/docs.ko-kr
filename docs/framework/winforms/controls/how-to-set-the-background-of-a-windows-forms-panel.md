---
title: 패널 배경 설정
description: 디자이너를 사용 하 여 Windows Forms 패널의 배경 색과 배경 이미지를 설정 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 109ff6184de9c79d1576207bbeb29ad939670b6f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173382"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="403be-103">방법: Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="403be-103">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="403be-104">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403be-104">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="403be-105"><xref:System.Windows.Forms.Control.BackColor%2A>속성은 레이블 및 라디오 단추와 같은 포함 된 컨트롤의 배경색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="403be-105">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="403be-106"><xref:System.Windows.Forms.Control.BackgroundImage%2A>속성이 설정 되지 않은 경우에는 <xref:System.Windows.Forms.Control.BackColor%2A> 선택이 전체 패널에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="403be-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="403be-107"><xref:System.Windows.Forms.Control.BackgroundImage%2A>속성이 설정 된 경우 포함 된 컨트롤 뒤에 이미지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="403be-107">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="403be-108">프로그래밍 방식으로 배경을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="403be-108">To set the background programmatically</span></span>  
  
1. <span data-ttu-id="403be-109">패널의 속성을 <xref:System.Windows.Forms.Control.BackColor%2A> 형식의 값으로 설정 합니다 <xref:System.Drawing.Color?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="403be-109">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. <span data-ttu-id="403be-110"><xref:System.Windows.Forms.Control.BackgroundImage%2A>클래스의 메서드를 사용 하 여 패널의 속성을 설정 합니다 <xref:System.Drawing.Image.FromFile%2A> <xref:System.Drawing.Image?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="403be-110">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="403be-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="403be-111">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="403be-112">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="403be-112">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="403be-113">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="403be-113">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
