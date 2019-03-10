---
title: Windows Forms에 사용자 도움말 통합
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715310"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="0fa9d-102">Windows Forms에 사용자 도움말 통합</span><span class="sxs-lookup"><span data-stu-id="0fa9d-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="0fa9d-103">Windows 기반 응용 프로그램을 구축 하는 필수적 이지만 흔히 간과 aspect 도움말 시스템은 이것은 사용자가 혼란의 시간에 대 한 도움말입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="0fa9d-104">각 Windows Forms에서 두 가지 유형의 도움말을 지원 하 여 제공 합니다 [HelpProvider 구성 요소](../controls/helpprovider-component-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="0fa9d-105">첫 번째 HTML 또는 HTML 도움말 1의 도움말 파일을 사용 하 여 사용자 가리키는 포함 됩니다. *x* 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="0fa9d-106">두 번째 표시할 수 있습니다 간단한 "What is/이"-개별 컨트롤; Help를 입력 합니다. 이 대화 상자에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="0fa9d-107">두 유형의 도움말 동일한 양식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="0fa9d-108">또한 합니다 [ToolTip 구성 요소](../controls/tooltip-component-windows-forms.md) Windows Forms에서 컨트롤에 대 한 개별 도움말을 제공 하기 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0fa9d-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0fa9d-109">In This Section</span></span>  
 [<span data-ttu-id="0fa9d-110">방법: Windows 응용 프로그램에서 도움말 제공</span><span class="sxs-lookup"><span data-stu-id="0fa9d-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="0fa9d-111">사용 하는 방법에 설명 합니다 `HelpProvider` 도움말 시스템에서 파일에 컨트롤을 연결할 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="0fa9d-112">방법: 팝업 도움말 표시</span><span class="sxs-lookup"><span data-stu-id="0fa9d-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="0fa9d-113">사용 하는 방법에 설명 합니다 `HelpProvider` Windows Forms에서 팝업 도움말을 표시할 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="0fa9d-114">ToolTip을 사용한 컨트롤 도움말</span><span class="sxs-lookup"><span data-stu-id="0fa9d-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="0fa9d-115">사용에 대해 설명 합니다 `ToolTip` 컨트롤의 도움말을 표시할 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0fa9d-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0fa9d-116">Related Sections</span></span>  
 [<span data-ttu-id="0fa9d-117">HelpProvider 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0fa9d-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="0fa9d-118">기본 사항을 설명 합니다 `HelpProvider` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="0fa9d-119">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0fa9d-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="0fa9d-120">기본 사항을 설명 합니다 `ToolTip` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="0fa9d-121">Windows Forms 개요</span><span class="sxs-lookup"><span data-stu-id="0fa9d-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="0fa9d-122">Windows Forms의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="0fa9d-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fa9d-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="0fa9d-124">Windows Forms에 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9d-124">Provides an overview of Windows Forms.</span></span>
