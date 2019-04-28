---
title: 내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b3f10fe472e449d39385facdbc716cba9b3f7382
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640497"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="66668-102">내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="66668-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="66668-103">표준 Windows Forms 도구 상자에서 컨트롤에 키보드 포커스 노출을 노출 및 화면 요소를 포함 하 여 내게 필요한 옵션 지침을 여러 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="66668-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="66668-104">내게 필요한 옵션에 대 한 미리 계획</span><span class="sxs-lookup"><span data-stu-id="66668-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="66668-105">컨트롤의 속성 표에 표시 된 것 처럼 다른 내게 필요한 옵션 지침을 지원 하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66668-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="66668-106">또한 프로그램 기능에 액세스할 수 있도록 메뉴를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66668-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="66668-107">컨트롤 속성</span><span class="sxs-lookup"><span data-stu-id="66668-107">Control Property</span></span>|<span data-ttu-id="66668-108">내게 필요한 옵션에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="66668-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="66668-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="66668-109">AccessibleDescription</span></span>|<span data-ttu-id="66668-110">에 대 한 설명 화면 읽기 프로그램과 같은 접근성 보조 기능에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66668-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="66668-111">접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="66668-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="66668-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="66668-112">AccessibleName</span></span>|<span data-ttu-id="66668-113">접근성 보조 기능에 보고 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="66668-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="66668-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="66668-114">AccessibleRole</span></span>|<span data-ttu-id="66668-115">사용자 인터페이스에서 해당 요소의 용도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66668-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="66668-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="66668-116">TabIndex</span></span>|<span data-ttu-id="66668-117">폼을 탐색할 수 있는 탐색 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66668-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="66668-118">탭 순서에서 앞에 즉시 연결 된 레이블을 해당 텍스트 상자와 같은 내장 레이블이 없는 컨트롤에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66668-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="66668-119">텍스트</span><span class="sxs-lookup"><span data-stu-id="66668-119">Text</span></span>|<span data-ttu-id="66668-120">액세스 키를 만들려면 "&" 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66668-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="66668-121">액세스 키를 사용 하는 기능에 대 한 문서화 된 키보드 액세스를 제공 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="66668-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="66668-122">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="66668-122">Font Size</span></span>|<span data-ttu-id="66668-123">글꼴 크기를 조정할 수 없는 경우 다음 설정 해야 10 포인트 이상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="66668-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="66668-124">폼의 글꼴 크기를 설정 하면 이후에 폼에 추가 하는 모든 컨트롤 같은 크기를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66668-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="66668-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="66668-125">Forecolor</span></span>|<span data-ttu-id="66668-126">이 속성을 기본값으로 설정, 사용자의 색상 기본 설정은 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66668-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="66668-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="66668-127">Backcolor</span></span>|<span data-ttu-id="66668-128">이 속성을 기본값으로 설정, 사용자의 색상 기본 설정은 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66668-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="66668-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="66668-129">BackgroundImage</span></span>|<span data-ttu-id="66668-130">텍스트를 더 쉽게 읽을 수 있도록 하려면이 속성을 비워둡니다.</span><span class="sxs-lookup"><span data-stu-id="66668-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66668-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="66668-131">See also</span></span>

- [<span data-ttu-id="66668-132">연습: 액세스할 수 있는 Windows 기반 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="66668-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](walkthrough-creating-an-accessible-windows-based-application.md)
