---
description: '자세한 정보: 애플리케이션의 정보 기록(Visual Basic)'
title: 응용 프로그램의 정보 기록
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 6e0adf45c12d98c8bc6d177d85accf9bee347f75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775073"
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="e51e3-103">애플리케이션의 정보 기록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e51e3-103">Logging Information from the Application (Visual Basic)</span></span>

<span data-ttu-id="e51e3-104">이 섹션에는 `My.Application.Log` 또는 `My.Log` 개체를 사용하여 애플리케이션의 정보를 기록하는 방법과 애플리케이션의 로깅 기능을 확장하는 방법을 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-104">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="e51e3-105">`Log` 개체는 애플리케이션의 로그 수신기에 정보를 쓰기 위한 메서드를 제공하고, `Log` 개체의 고급 `TraceSource` 속성은 자세한 구성 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-105">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="e51e3-106">`Log` 개체는 애플리케이션의 구성 파일에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-106">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="e51e3-107">`My.Log` 개체는 ASP.NET 애플리케이션에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-107">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="e51e3-108">클라이언트 애플리케이션의 경우 `My.Application.Log`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-108">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="e51e3-109">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e51e3-109">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e51e3-110">작업</span><span class="sxs-lookup"><span data-stu-id="e51e3-110">Tasks</span></span>  
  
|<span data-ttu-id="e51e3-111">대상</span><span class="sxs-lookup"><span data-stu-id="e51e3-111">To</span></span>|<span data-ttu-id="e51e3-112">참조 항목</span><span class="sxs-lookup"><span data-stu-id="e51e3-112">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="e51e3-113">애플리케이션의 로그에 이벤트 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-113">Write event information to the application's logs.</span></span>|[<span data-ttu-id="e51e3-114">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="e51e3-114">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)|  
|<span data-ttu-id="e51e3-115">애플리케이션의 로그에 예외 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-115">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="e51e3-116">방법: 로그 예외</span><span class="sxs-lookup"><span data-stu-id="e51e3-116">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)|  
|<span data-ttu-id="e51e3-117">애플리케이션을 시작 및 종료할 때 애플리케이션의 로그에 추적 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-117">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="e51e3-118">방법: 애플리케이션이 시작 또는 종료될 때 메시지 기록</span><span class="sxs-lookup"><span data-stu-id="e51e3-118">How to: Log Messages When the Application Starts or Shuts Down</span></span>](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="e51e3-119">텍스트 파일에 정보를 쓰도록 `My.Application.Log`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-119">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="e51e3-120">방법: 텍스트 파일에 이벤트 정보 쓰기</span><span class="sxs-lookup"><span data-stu-id="e51e3-120">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="e51e3-121">이벤트 로그에 정보를 쓰도록 `My.Application.Log`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-121">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="e51e3-122">방법: 애플리케이션 이벤트 로그에 쓰기</span><span class="sxs-lookup"><span data-stu-id="e51e3-122">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="e51e3-123">`My.Application.Log`가 정보를 쓰는 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-123">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="e51e3-124">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="e51e3-124">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="e51e3-125">`My.Application.Log`가 정보를 쓰는 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-125">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="e51e3-126">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="e51e3-126">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="e51e3-127">`My.Application.Log`에 대한 사용자 지정 로그 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-127">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="e51e3-128">연습: 사용자 지정 로그 수신기 만들기</span><span class="sxs-lookup"><span data-stu-id="e51e3-128">Walkthrough: Creating Custom Log Listeners</span></span>](walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="e51e3-129">`My.Application.Log` 로그의 출력을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="e51e3-129">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="e51e3-130">연습: My.Application.Log 출력 필터링</span><span class="sxs-lookup"><span data-stu-id="e51e3-130">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e51e3-131">참조</span><span class="sxs-lookup"><span data-stu-id="e51e3-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="e51e3-132">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="e51e3-132">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="e51e3-133">문제 해결: 로그 수신기</span><span class="sxs-lookup"><span data-stu-id="e51e3-133">Troubleshooting: Log Listeners</span></span>](troubleshooting-log-listeners.md)
