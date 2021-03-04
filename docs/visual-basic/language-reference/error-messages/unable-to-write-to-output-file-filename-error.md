---
description: "자세히 알아보기: BC31019: 출력 파일 ' '에 쓸 수 없습니다 <filename> . <error>"
title: "'<filename>' 출력 파일에 쓸 수 없습니다. <error>"
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: 86ddd01764d51c3050186e99e047edb8aba158eb
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104808"
---
# <a name="bc31019-unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="fd866-103">BC31019: 출력 파일 ' '에 쓸 수 없습니다 \<filename> . \<error></span><span class="sxs-lookup"><span data-stu-id="fd866-103">BC31019: Unable to write to output file '\<filename>': \<error></span></span>

<span data-ttu-id="fd866-104">파일을 만드는 동안 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-104">There was a problem creating the file.</span></span>

 <span data-ttu-id="fd866-105">출력 파일을 쓰기 위해 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-105">An output file cannot be opened for writing.</span></span> <span data-ttu-id="fd866-106">파일 또는 파일이 포함된 폴더가 다른 프로세스에서 단독으로 사용되도록 열려 있거나 읽기 전용 특성이 설정되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-106">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>

 <span data-ttu-id="fd866-107">파일이 단독으로 열리는 일반적인 상황은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-107">Common situations where a file is opened exclusively are:</span></span>

- <span data-ttu-id="fd866-108">애플리케이션이 이미 실행 중이며 해당 파일을 사용 중인 경우.</span><span class="sxs-lookup"><span data-stu-id="fd866-108">The application is already running and using its files.</span></span> <span data-ttu-id="fd866-109">이 문제를 해결하려면 애플리케이션이 실행되지 않고 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-109">To solve this problem, make sure that the application is not running.</span></span>

- <span data-ttu-id="fd866-110">다른 애플리케이션이 파일을 연 경우.</span><span class="sxs-lookup"><span data-stu-id="fd866-110">Another application has opened the file.</span></span> <span data-ttu-id="fd866-111">이 문제를 해결하려면 다른 애플리케이션이 파일에 액세스하지 않고 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-111">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="fd866-112">파일에 액세스 중인 애플리케이션이 확실하지 않은 경우도 있습니다. 이러한 경우 애플리케이션을 종료하는 가장 쉬운 방법은 컴퓨터를 다시 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-112">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>

 <span data-ttu-id="fd866-113">프로젝트 출력 파일 중 하나라도 읽기 전용으로 표시되어 있으면 이 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-113">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>

 <span data-ttu-id="fd866-114">**오류 ID:** BC31019</span><span class="sxs-lookup"><span data-stu-id="fd866-114">**Error ID:** BC31019</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="fd866-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fd866-115">To correct this error</span></span>

1. <span data-ttu-id="fd866-116">프로그램을 다시 컴파일하여 오류가 다시 발생하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-116">Compile the program again to see if the error recurs.</span></span>

2. <span data-ttu-id="fd866-117">오류가 계속 되 면 작업을 저장 하 고 Visual Studio를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-117">If the error continues, save your work and restart Visual Studio.</span></span>

3. <span data-ttu-id="fd866-118">오류가 계속 발생하면 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-118">If the error continues, restart the computer.</span></span>

4. <span data-ttu-id="fd866-119">오류가 다시 발생 하면 Visual Basic를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-119">If the error recurs, reinstall Visual Basic.</span></span>

5. <span data-ttu-id="fd866-120">다시 설치 후에도 오류가 계속 발생하면 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-120">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>

### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="fd866-121">파일 탐색기에서 파일 특성을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="fd866-121">To check file attributes in File Explorer</span></span>

1. <span data-ttu-id="fd866-122">원하는 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-122">Open the folder you are interested in.</span></span>

2. <span data-ttu-id="fd866-123">**보기** 아이콘을 클릭 하 고 **세부 정보** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-123">Click the **Views** icon and choose **Details**.</span></span>

3. <span data-ttu-id="fd866-124">열 머리글을 마우스 오른쪽 단추로 클릭 하 고 드롭다운 목록에서 **특성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-124">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>

### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="fd866-125">파일이나 폴더의 특성을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="fd866-125">To change the attributes of a file or folder</span></span>

1. <span data-ttu-id="fd866-126">**파일 탐색기** 에서 파일 또는 폴더를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-126">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>

2. <span data-ttu-id="fd866-127">**일반** 탭의 **특성** 섹션에서 **읽기 전용** 상자의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-127">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>

3. <span data-ttu-id="fd866-128">**확인** 을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd866-128">Press **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd866-129">참조</span><span class="sxs-lookup"><span data-stu-id="fd866-129">See also</span></span>

- [<span data-ttu-id="fd866-130">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="fd866-130">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
