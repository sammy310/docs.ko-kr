---
title: Windows Forms 디자이너의 디자인 타임 오류
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
ms.openlocfilehash: 64a0b8d0d0d9f0cc2bc2a841b999af58f29b4f75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718053"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="19f5d-102">Windows Forms 디자이너의 디자인 타임 오류</span><span class="sxs-lookup"><span data-stu-id="19f5d-102">Design-Time Errors in the Windows Forms Designer</span></span>
<span data-ttu-id="19f5d-103">이 문서에서는 Windows Forms 디자이너를 로드하지 못할 때 Microsoft Visual Studio에 표시되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-103">This topic explains the meaning and use of the design-time error list that appears in Microsoft Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="19f5d-104">이 오류 목록이 표시되면 디자이너에서 버그가 아닌 코드의 오류를 수정하는 보조 기능으로 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>  
  
 <span data-ttu-id="19f5d-105">이 오류 목록의 기본적인 이해를 통해 오류에 대한 자세한 정보를 제공하고 가능한 해결 방법을 제안하여 애플리케이션을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>  
  
## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="19f5d-106">디자인 타임 오류 목록 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19f5d-106">The Design-Time Error List Interface</span></span>  
 <span data-ttu-id="19f5d-107">Windows Forms 디자이너를 로드하지 못하는 경우 오류 목록이 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-107">If the Windows Forms Designer fails to load, an error list will appear in the designer.</span></span> <span data-ttu-id="19f5d-108">오류는 범주로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-108">The errors are grouped into categories.</span></span> <span data-ttu-id="19f5d-109">예를 들어 선언되지 않은 변수의 네 가지 인스턴스가 있는 경우 동일한 오류 범주로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="19f5d-110">각 오류 범주는 해당 오류를 요약한 간단한 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-110">Each error category includes a brief description that summarizes the error.</span></span>  
  
 <span data-ttu-id="19f5d-111">오류 범주 머리글을 클릭하거나 확장/축소 펼침 단추를 클릭하여 오류 범주를 확장하거나 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="19f5d-112">오류 범주를 확장하면 다음과 같은 추가 도움말이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-112">When you expand an error category, the following additional help is displayed:</span></span>  
  
-   <span data-ttu-id="19f5d-113">이 오류의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="19f5d-113">Instances of this error.</span></span>  
  
-   <span data-ttu-id="19f5d-114">이 오류에 대한 도움말</span><span class="sxs-lookup"><span data-stu-id="19f5d-114">Help with this error.</span></span>  
  
-   <span data-ttu-id="19f5d-115">이 오류에 대한 포럼 게시물</span><span class="sxs-lookup"><span data-stu-id="19f5d-115">Forum posts about this error.</span></span>  
  
### <a name="instances-of-this-error"></a><span data-ttu-id="19f5d-116">이 오류의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="19f5d-116">Instances of This Error</span></span>  
 <span data-ttu-id="19f5d-117">추가 도움말은 현재 프로젝트에서 오류 메시지의 모든 인스턴스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="19f5d-118">대부분의 오류는 다음과 같은 형식으로 정확한 위치를 포함합니다. *[프로젝트 이름]* *[양식 이름]* 줄:*[줄 번호]* 열:*[열 번호]*</span><span class="sxs-lookup"><span data-stu-id="19f5d-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="19f5d-119">**코드로 이동** 링크를 통해 오류가 발생하는 코드의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>  
  
 <span data-ttu-id="19f5d-120">호출 스택이 오류와 연결되는 경우 **호출 스택 표시** 링크를 클릭하면 오류를 더 확장하여 호출 스택을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="19f5d-121">스택 검사는 중요한 디버깅 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="19f5d-122">예를 들어 오류가 발생하기 전에 호출된 함수를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="19f5d-123">호출 스택은 선택하여 복사하고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-123">The call stack is selectable so that you can copy and save it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19f5d-124">Visual Basic에서 디자인 타임 오류 목록은 둘 이상의 오류를 표시하지 않지만 동일한 오류의 여러 인스턴스를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="19f5d-125">Visual C++에서 오류에는 이동 코드 링크/줄 번호 링크가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>  
  
### <a name="help-with-this-error"></a><span data-ttu-id="19f5d-126">이 오류에 대한 도움말</span><span class="sxs-lookup"><span data-stu-id="19f5d-126">Help with This Error</span></span>  
 <span data-ttu-id="19f5d-127">이 오류에 관련된 MSDN 도움말 항목에 대한 링크가 포함되는 경우 추가 도움말은 도움말 항목에 대한 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-127">If the error contains a link to an associated MSDN help topic, the additional help will include a link to the help topic.</span></span> <span data-ttu-id="19f5d-128">링크를 클릭하면 Visual Studio에 관련된 도움말 항목이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-128">When you click the link, the associated help topic appears in Visual Studio.</span></span>  
  
### <a name="forum-posts-about-this-error"></a><span data-ttu-id="19f5d-129">이 오류에 대한 포럼 게시물</span><span class="sxs-lookup"><span data-stu-id="19f5d-129">Forum posts about this error</span></span>  
 <span data-ttu-id="19f5d-130">추가 도움말은 오류와 관련된 MSDN 포럼 게시물에 대한 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-130">The additional help will include a link to MSDN forum posts related to the error.</span></span> <span data-ttu-id="19f5d-131">포럼은 오류 메시지의 문자열에 따라 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-131">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="19f5d-132">다음과 같은 포럼을 검색하도록 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-132">You can also try searching the following forums:</span></span>  
  
-   [<span data-ttu-id="19f5d-133">Windows Forms 디자이너 포럼</span><span class="sxs-lookup"><span data-stu-id="19f5d-133">Windows Forms Designer Forum</span></span>](https://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [<span data-ttu-id="19f5d-134">Windows Forms 포럼</span><span class="sxs-lookup"><span data-stu-id="19f5d-134">Windows Forms Forums</span></span>](https://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a><span data-ttu-id="19f5d-135">무시 후 계속</span><span class="sxs-lookup"><span data-stu-id="19f5d-135">Ignore and Continue</span></span>  
 <span data-ttu-id="19f5d-136">오류 상태를 무시하고 디자이너를 계속 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-136">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="19f5d-137">이 작업을 선택하면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-137">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="19f5d-138">예를 들어 컨트롤이 디자인 화면에 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f5d-138">For example, controls may not appear on the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f5d-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="19f5d-139">See also</span></span>
- <span data-ttu-id="19f5d-140">[디자인 타임 개발 문제 해결](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="19f5d-140">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="19f5d-141">컨트롤 및 구성 요소 제작 문제 해결</span><span class="sxs-lookup"><span data-stu-id="19f5d-141">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="19f5d-142">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="19f5d-142">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="19f5d-143">[Windows Forms 디자이너 오류 메시지](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19f5d-143">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>
