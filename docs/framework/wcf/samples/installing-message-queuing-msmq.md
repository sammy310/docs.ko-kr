---
title: 메시지 큐(MSMQ) 설치
description: 일회성 설치 절차의 일부로 WFC 샘플과 함께 사용할 메시지 큐 4.0 및 메시지 큐 3.0을 설치 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: bf33a5cd899bf2d7ef4947c51ac1723c8eb80c29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281874"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="3c669-103">메시지 큐(MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="3c669-103">Installing Message Queuing (MSMQ)</span></span>

<span data-ttu-id="3c669-104">다음 절차에서는 메시지 큐 4.0 및 메시지 큐 3.0을 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-104">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c669-105">메시지 큐 4.0은 Windows XP 및 Windows Server 2003에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-105">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="3c669-106">Windows Server 2008 또는 Windows Server 2008 R2에 메시지 큐 4.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="3c669-106">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="3c669-107">서버 관리자에서 **기능** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-107">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="3c669-108">오른쪽 창의 **기능 요약** 에서 **기능 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-108">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="3c669-109">결과 창에서 **메시지 큐** 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-109">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="3c669-110">**메시지 큐 서비스** 를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-110">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="3c669-111">**디렉터리 서비스 통합** (도메인에 가입 된 컴퓨터의 경우)을 클릭 한 다음 **HTTP 지원** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-111">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="3c669-112">**다음** 을 클릭 한 후 **설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-112">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="3c669-113">Windows 7 또는 Windows Vista에 메시지 큐 4.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="3c669-113">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="3c669-114">**제어판** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-114">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="3c669-115">**프로그램** 을 클릭 하 고 **프로그램 및 기능** 에서 **Windows 기능 사용/사용 안 함** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-115">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="3c669-116">MSMQ(Microsoft Message Queue) Server, MSMQ(Microsoft Message Queue) Server Core를 차례로 확장한 후 설치할 다음과 같은 메시지 큐 기능 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-116">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="3c669-117">MSMQ Active Directory 도메인 서비스 통합(도메인에 연결된 컴퓨터의 경우)</span><span class="sxs-lookup"><span data-stu-id="3c669-117">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="3c669-118">MSMQ HTTP 지원</span><span class="sxs-lookup"><span data-stu-id="3c669-118">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="3c669-119">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-119">Click **OK**.</span></span>  
  
5. <span data-ttu-id="3c669-120">컴퓨터를 다시 시작할지 묻는 메시지가 표시 되 면 **확인** 을 클릭 하 여 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-120">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="3c669-121">Windows XP 및 Windows Server 2003에 메시지 큐 3.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="3c669-121">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="3c669-122">**제어판** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-122">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="3c669-123">**프로그램 추가/제거** 를 클릭 한 다음 **Windows 구성 요소 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-123">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="3c669-124">메시지 큐를 선택 하 고 **세부 정보** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-124">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3c669-125">Windows Server 2003를 실행 하는 경우 응용 프로그램 서버를 선택 하 여 메시지 큐에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-125">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="3c669-126">MSMQ HTTP 지원 옵션이 자세히 페이지에 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-126">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="3c669-127">**확인** 을 클릭 하 여 세부 정보 페이지를 종료 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-127">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="3c669-128">설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-128">Complete the installation.</span></span>  
  
6. <span data-ttu-id="3c669-129">컴퓨터를 다시 시작할지 묻는 메시지가 표시 되 면 **확인** 을 클릭 하 여 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c669-129">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c669-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c669-130">See also</span></span>

- [<span data-ttu-id="3c669-131">설치 지침</span><span class="sxs-lookup"><span data-stu-id="3c669-131">Set-Up Instructions</span></span>](set-up-instructions.md)
