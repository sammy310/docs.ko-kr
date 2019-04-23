---
title: 서비스 작업 기간 확인
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772782"
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="389e4-102">서비스 작업 기간 확인</span><span class="sxs-lookup"><span data-stu-id="389e4-102">Determining service operation duration</span></span>
<span data-ttu-id="389e4-103">분석 추적을 Windows Communication Foundation (WCF) 응용 프로그램에서 사용 하는 경우 서비스 작업에 대 한 실행 기간 이벤트 로그를 검사 하 여 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-103">If analytic tracing is enabled in a Windows Communication Foundation (WCF) application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="389e4-104">이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="389e4-105">서비스 작업 실행 기간 확인</span><span class="sxs-lookup"><span data-stu-id="389e4-105">Determining service operation execution duration</span></span>  
  
1. <span data-ttu-id="389e4-106">클릭 하 여 이벤트 뷰어를 엽니다 **시작**를 **실행**를 입력 하 고 `eventvwr.exe`입니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2. <span data-ttu-id="389e4-107">분석 추적을 활성화 하지 않은 경우 확장 **Applications and Services Logs**를 **Microsoft**하십시오 **Windows**, **응용 프로그램 서버-응용 프로그램** .</span><span class="sxs-lookup"><span data-stu-id="389e4-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="389e4-108">선택 **뷰**하십시오 **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="389e4-109">마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="389e4-110">서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3. <span data-ttu-id="389e4-111">서비스 프로젝트 및 해당 서비스와 상호 작용 하는 클라이언트 프로젝트를 포함 하는 WCF 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-111">Next, open a WCF application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="389e4-112">수행 하 여 이러한 응용 프로그램을 만들 수 있습니다 합니다 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="389e4-113">설치 하는 WCF 샘플에 있는 경우 열 수 있습니다 합니다 [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-113">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4. <span data-ttu-id="389e4-114">키를 눌러 서버 응용 프로그램을 실행 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="389e4-115">마우스 오른쪽 단추로 클릭 하 여 클라이언트 응용 프로그램을 실행 합니다 **클라이언트** 프로젝트를 선택 하 고 **디버그**를 **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5. <span data-ttu-id="389e4-116">이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="389e4-117">이벤트 ID를 사용 하 여 이벤트를 검색할 [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="389e4-118">이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="389e4-119">다음 이벤트는 Add 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389e4-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
