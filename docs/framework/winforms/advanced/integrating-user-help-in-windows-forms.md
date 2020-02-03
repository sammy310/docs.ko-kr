---
title: 사용자 도움말 통합
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: c402615d68c75327613d21bd35f1587b10f1dbf3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731570"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="9b204-102">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="9b204-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="9b204-103">Windows 기반 응용 프로그램을 구축 하는 데 있어 중요 한 점은 간과 될 때 사용자가 도움을 받을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="9b204-104">Windows Forms는 [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)에서 제공 하는 두 가지 유형의 도움말을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="9b204-105">첫 번째 방법은 사용자가 HTML 또는 HTML 도움말 1의 도움말 파일을 가리키는 것입니다. *x* 또는 큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="9b204-106">두 번째는 개별 컨트롤에 대 한 간략 한 "What 's" 형식 도움말을 표시할 수 있습니다. 이 기능은 대화 상자에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="9b204-107">동일한 폼에서 두 가지 유형의 도움말을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="9b204-108">또한 [도구 설명 구성 요소](../controls/tooltip-component-windows-forms.md) 를 사용 하 여 Windows Forms 컨트롤에 대 한 개별 도움말을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b204-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9b204-109">In This Section</span></span>  
 [<span data-ttu-id="9b204-110">방법: Windows 애플리케이션에서 도움말 제공</span><span class="sxs-lookup"><span data-stu-id="9b204-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="9b204-111">`HelpProvider` 구성 요소를 사용 하 여 도움말 시스템의 파일에 컨트롤을 연결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="9b204-112">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="9b204-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="9b204-113">`HelpProvider` 구성 요소를 사용 하 여 Windows Forms에 팝업 도움말을 표시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="9b204-114">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="9b204-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="9b204-115">`ToolTip` 구성 요소를 사용 하 여 컨트롤별 도움말을 표시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9b204-116">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="9b204-116">Related Sections</span></span>  
 [<span data-ttu-id="9b204-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9b204-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="9b204-118">`HelpProvider` 구성 요소의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="9b204-119">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9b204-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="9b204-120">`ToolTip` 구성 요소의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="9b204-121">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="9b204-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="9b204-122">Windows Forms의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="9b204-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b204-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="9b204-124">Windows Forms에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b204-124">Provides an overview of Windows Forms.</span></span>
