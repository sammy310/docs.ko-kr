---
description: '자세한 정보: 서비스 작업 기간 결정'
title: 서비스 작업 기간 확인
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: e9dd9ee4113ee4b4521afb6dfaf6a913e72ea5d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798812"
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="133ed-103">서비스 작업 기간 확인</span><span class="sxs-lookup"><span data-stu-id="133ed-103">Determining service operation duration</span></span>

<span data-ttu-id="133ed-104">WCF (Windows Communication Foundation) 응용 프로그램에서 분석 추적을 사용 하는 경우 이벤트 로그를 검사 하 여 서비스 작업에 대 한 실행 기간을 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-104">If analytic tracing is enabled in a Windows Communication Foundation (WCF) application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="133ed-105">이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-105">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="133ed-106">서비스 작업 실행 기간 확인</span><span class="sxs-lookup"><span data-stu-id="133ed-106">Determining service operation execution duration</span></span>  
  
1. <span data-ttu-id="133ed-107">**시작**, **실행** 을 차례로 클릭 하 고를 입력 하 여 이벤트 뷰어를 엽니다 `eventvwr.exe` .</span><span class="sxs-lookup"><span data-stu-id="133ed-107">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2. <span data-ttu-id="133ed-108">분석 추적을 사용 하도록 설정 하지 않은 경우 **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-** 응용 프로그램을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-108">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="133ed-109">**보기**, **분석 및 디버그 로그 표시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-109">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="133ed-110">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-110">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="133ed-111">서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-111">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3. <span data-ttu-id="133ed-112">그런 다음 서비스 프로젝트 및 서비스와 상호 작용 하는 클라이언트 프로젝트를 포함 하는 WCF 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-112">Next, open a WCF application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="133ed-113">초보자를 위한 [자습서](../../getting-started-tutorial.md)에 따라 이러한 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-113">You can create such an application by following the [Getting Started Tutorial](../../getting-started-tutorial.md).</span></span>  <span data-ttu-id="133ed-114">WCF 샘플을 설치한 경우 자습서에서 만든 완료 된 프로젝트를 포함 하는 [시작](../../samples/getting-started-sample.md)을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-114">If you have the WCF samples installed, you can open the [Getting Started](../../samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4. <span data-ttu-id="133ed-115">**F5** 키를 눌러 서버 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-115">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="133ed-116">**클라이언트** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **디버그**, **새 인스턴스 시작** 을 차례로 선택 하 여 클라이언트 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-116">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5. <span data-ttu-id="133ed-117">이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-117">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="133ed-118">이벤트 ID가 [214-OperationCompleted](214-operationcompleted.md)인 이벤트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-118">Look for events with Event ID [214 - OperationCompleted](214-operationcompleted.md).</span></span>  <span data-ttu-id="133ed-119">이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-119">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="133ed-120">다음 이벤트는 Add 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="133ed-120">The following event shows the duration of an Add operation.</span></span>  
  
    ```output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
