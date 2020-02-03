---
title: 컨트롤의 내게 필요한 옵션 속성
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743430"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="21a47-102">내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="21a47-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="21a47-103">Windows Forms에 대 한 표준 도구 상자의 컨트롤은 키보드 포커스를 표시 하 고 화면 요소를 표시 하는 등 많은 내게 필요한 옵션 지침을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="21a47-104">접근성에 대 한 미리 계획</span><span class="sxs-lookup"><span data-stu-id="21a47-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="21a47-105">컨트롤의 속성을 사용 하 여 다음 표에 나와 있는 것 처럼 다른 접근성 지침을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="21a47-106">또한 메뉴를 사용 하 여 프로그램 기능에 대 한 액세스를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="21a47-107">컨트롤 속성</span><span class="sxs-lookup"><span data-stu-id="21a47-107">Control Property</span></span>|<span data-ttu-id="21a47-108">내게 필요한 옵션에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="21a47-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="21a47-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="21a47-109">AccessibleDescription</span></span>|<span data-ttu-id="21a47-110">설명은 화면 판독기와 같은 내게 필요한 옵션 지원 기능에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="21a47-111">접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="21a47-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="21a47-112">AccessibleName</span></span>|<span data-ttu-id="21a47-113">내게 필요한 옵션 지원 기능에 보고 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="21a47-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="21a47-114">AccessibleRole</span></span>|<span data-ttu-id="21a47-115">사용자 인터페이스에서 요소를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="21a47-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="21a47-116">TabIndex</span></span>|<span data-ttu-id="21a47-117">폼을 통해 합리적인 탐색 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="21a47-118">텍스트 상자와 같은 내장 레이블이 없는 컨트롤은 탭 순서에서 연결 된 레이블을 바로 앞에 오도록 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="21a47-119">Text</span><span class="sxs-lookup"><span data-stu-id="21a47-119">Text</span></span>|<span data-ttu-id="21a47-120">"&" 문자를 사용 하 여 액세스 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="21a47-121">액세스 키 사용은 설명서 키보드의 기능 액세스를 제공 하는 데 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="21a47-122">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="21a47-122">Font Size</span></span>|<span data-ttu-id="21a47-123">글꼴 크기를 조정할 수 없는 경우 10 점으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="21a47-124">폼의 글꼴 크기를 설정 하면 이후에 폼에 추가 된 모든 컨트롤의 크기가 동일 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="21a47-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="21a47-125">Forecolor</span></span>|<span data-ttu-id="21a47-126">이 속성을 기본값으로 설정 하면 사용자의 색 기본 설정이 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="21a47-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="21a47-127">Backcolor</span></span>|<span data-ttu-id="21a47-128">이 속성을 기본값으로 설정 하면 사용자의 색 기본 설정이 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="21a47-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="21a47-129">BackgroundImage</span></span>|<span data-ttu-id="21a47-130">텍스트를 더 쉽게 읽을 수 있도록 하려면이 속성을 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="21a47-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21a47-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21a47-131">See also</span></span>

- [<span data-ttu-id="21a47-132">연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="21a47-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)
