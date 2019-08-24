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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015967"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a><span data-ttu-id="b5ca7-102">Windows Forms 디자이너의 디자인 타임 오류</span><span class="sxs-lookup"><span data-stu-id="b5ca7-102">Design-time errors in the Windows Forms Designer</span></span>

<span data-ttu-id="b5ca7-103">이 항목에서는 Windows Forms 디자이너 로드 되지 않을 때 Visual Studio에 표시 되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-103">This topic explains the meaning and use of the design-time error list that appears in Visual Studio when the Windows Forms Designer fails to load.</span></span> <span data-ttu-id="b5ca7-104">이 오류 목록이 표시되면 디자이너에서 버그가 아닌 코드의 오류를 수정하는 보조 기능으로 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-104">If this error list appears, you should not interpret it as a bug in the designer, but as an aid to correcting errors in your code.</span></span>

<span data-ttu-id="b5ca7-105">이 오류 목록의 기본적인 이해를 통해 오류에 대한 자세한 정보를 제공하고 가능한 해결 방법을 제안하여 애플리케이션을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-105">A basic understanding of this error list will help you debug your applications by providing detailed information about the errors and suggesting possible solutions.</span></span>

## <a name="the-design-time-error-list-interface"></a><span data-ttu-id="b5ca7-106">디자인 타임 오류 목록 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-106">The design-time error list interface</span></span>

<span data-ttu-id="b5ca7-107">Windows Forms 디자이너 로드 되지 않으면 디자이너에 오류 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-107">If the Windows Forms Designer fails to load, an error list appears in the designer.</span></span> <span data-ttu-id="b5ca7-108">오류는 범주로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-108">The errors are grouped into categories.</span></span> <span data-ttu-id="b5ca7-109">예를 들어 선언되지 않은 변수의 네 가지 인스턴스가 있는 경우 동일한 오류 범주로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-109">For example, if you have four instances of undeclared variables, these will be grouped into the same error category.</span></span> <span data-ttu-id="b5ca7-110">각 오류 범주는 해당 오류를 요약한 간단한 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-110">Each error category includes a brief description that summarizes the error.</span></span>

<span data-ttu-id="b5ca7-111">오류 범주 머리글을 클릭하거나 확장/축소 펼침 단추를 클릭하여 오류 범주를 확장하거나 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-111">You can expand or collapse an error category by either clicking on the error category heading or by clicking the expand/collapse chevron.</span></span> <span data-ttu-id="b5ca7-112">오류 범주를 확장하면 다음과 같은 추가 도움말이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-112">When you expand an error category, the following additional help is displayed:</span></span>

- <span data-ttu-id="b5ca7-113">이 오류의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="b5ca7-113">Instances of this error.</span></span>

- <span data-ttu-id="b5ca7-114">이 오류에 대한 도움말</span><span class="sxs-lookup"><span data-stu-id="b5ca7-114">Help with this error.</span></span>

- <span data-ttu-id="b5ca7-115">이 오류에 대한 포럼 게시물</span><span class="sxs-lookup"><span data-stu-id="b5ca7-115">Forum posts about this error.</span></span>

### <a name="instances-of-this-error"></a><span data-ttu-id="b5ca7-116">이 오류의 인스턴스</span><span class="sxs-lookup"><span data-stu-id="b5ca7-116">Instances of this error</span></span>

<span data-ttu-id="b5ca7-117">추가 도움말은 현재 프로젝트에서 오류 메시지의 모든 인스턴스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-117">The additional help list all instances of the error in your current project.</span></span> <span data-ttu-id="b5ca7-118">대부분의 오류는 다음과 같은 형식으로 정확한 위치를 포함합니다. *[프로젝트 이름]* *[양식 이름]* 줄: *[줄 번호]* 열: *[열 번호]*</span><span class="sxs-lookup"><span data-stu-id="b5ca7-118">Many errors include an exact location in the following format: *[Project Name]* *[Form Name]* Line:*[Line Number]* Column:*[Column Number]*.</span></span> <span data-ttu-id="b5ca7-119">**코드로 이동** 링크를 통해 오류가 발생하는 코드의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-119">The **Go to code** link takes you to the location in your code where the error occurs.</span></span>

<span data-ttu-id="b5ca7-120">호출 스택이 오류와 연결되는 경우 **호출 스택 표시** 링크를 클릭하면 오류를 더 확장하여 호출 스택을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-120">If a call stack is associated with the error, you can click the **Show Call Stack** link, which further expands the error to show the call stack.</span></span> <span data-ttu-id="b5ca7-121">스택 검사는 중요한 디버깅 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-121">Examining the stack can provide valuable debugging information.</span></span> <span data-ttu-id="b5ca7-122">예를 들어 오류가 발생하기 전에 호출된 함수를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-122">For example, you can track the functions that were called before the error occurred.</span></span> <span data-ttu-id="b5ca7-123">호출 스택은 선택하여 복사하고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-123">The call stack is selectable so that you can copy and save it.</span></span>

> [!NOTE]
> <span data-ttu-id="b5ca7-124">Visual Basic에서 디자인 타임 오류 목록은 둘 이상의 오류를 표시하지 않지만 동일한 오류의 여러 인스턴스를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-124">In Visual Basic, the design-time error list does not display more than one error, but it may display multiple instances of the same error.</span></span> <span data-ttu-id="b5ca7-125">Visual C++에서 오류에는 이동 코드 링크/줄 번호 링크가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-125">In Visual C++, the errors do not have goto code links/line number links.</span></span>

### <a name="forum-posts-about-this-error"></a><span data-ttu-id="b5ca7-126">이 오류에 대한 포럼 게시물</span><span class="sxs-lookup"><span data-stu-id="b5ca7-126">Forum posts about this error</span></span>

<span data-ttu-id="b5ca7-127">추가 도움말에는 오류와 관련 된 포럼 게시물에 대 한 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-127">The additional help includes a link to forum posts related to the error.</span></span> <span data-ttu-id="b5ca7-128">포럼은 오류 메시지의 문자열에 따라 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-128">The forums are searched based on the string of the error message.</span></span> <span data-ttu-id="b5ca7-129">다음 포럼에서 검색을 시도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-129">You can also try searching on the following forums:</span></span>

- [<span data-ttu-id="b5ca7-130">Windows Forms 디자이너 포럼</span><span class="sxs-lookup"><span data-stu-id="b5ca7-130">Windows Forms Designer forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [<span data-ttu-id="b5ca7-131">Windows Forms 포럼</span><span class="sxs-lookup"><span data-stu-id="b5ca7-131">Windows Forms forum</span></span>](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a><span data-ttu-id="b5ca7-132">무시 후 계속</span><span class="sxs-lookup"><span data-stu-id="b5ca7-132">Ignore and continue</span></span>

<span data-ttu-id="b5ca7-133">오류 상태를 무시하고 디자이너를 계속 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-133">You can choose to ignore the error condition and continue loading the designer.</span></span> <span data-ttu-id="b5ca7-134">이 작업을 선택하면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-134">Choosing this action may result in unexpected behavior.</span></span> <span data-ttu-id="b5ca7-135">예를 들어 컨트롤이 디자인 화면에 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5ca7-135">For example, controls may not appear on the design surface.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ca7-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5ca7-136">See also</span></span>

- <span data-ttu-id="b5ca7-137">[디자인 타임 개발 문제 해결](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="b5ca7-137">[Troubleshooting Design-Time Development](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))</span></span>
- [<span data-ttu-id="b5ca7-138">컨트롤 및 구성 요소 제작 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b5ca7-138">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)
- [<span data-ttu-id="b5ca7-139">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="b5ca7-139">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- <span data-ttu-id="b5ca7-140">[Windows Forms 디자이너 오류 메시지](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b5ca7-140">[Windows Forms Designer Error Messages](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))</span></span>
