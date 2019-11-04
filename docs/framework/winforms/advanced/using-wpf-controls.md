---
title: WPF 컨트롤 사용
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460699"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="88544-102">Windows Forms apps에서 WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="88544-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="88544-103">Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation (WPF) 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88544-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="88544-104">두 가지 서로 다른 뷰 기술 이지만 원활 하 게 상호 운용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88544-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="88544-105">Visual Studio의 Windows Forms 디자이너은 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88544-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="88544-106">WPF 컨트롤은 <xref:System.Windows.Forms.Integration.ElementHost>라는 특수 한 Windows Forms 컨트롤에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="88544-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="88544-107">이 컨트롤을 통해 WPF 컨트롤은 폼의 레이아웃에 참여 하 고 키보드 및 마우스 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88544-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="88544-108">디자인 타임에 Windows Forms 컨트롤과 동일한 방식으로 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88544-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="88544-109">WPF 기반 응용 프로그램에서 Windows Forms 컨트롤을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88544-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="88544-110">자세한 내용은 [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88544-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="88544-111">참조</span><span class="sxs-lookup"><span data-stu-id="88544-111">See also</span></span>

- [<span data-ttu-id="88544-112">WPF 및 Windows Forms 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="88544-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
