---
description: '자세히 알아보기: 인터넷 정보 서비스 호스팅 지침'
title: 인터넷 정보 서비스 호스팅 지침
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 51f5230ecbb8eaf4a909c5c09366680b8c555165
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726379"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="727bb-103">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="727bb-103">Internet Information Service Hosting Instructions</span></span>

<span data-ttu-id="727bb-104">IIS(인터넷 정보 서비스)에서 호스팅하는 샘플을 실행하려면 IIS가 올바르게 설치되어 있고 실행 중인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-104">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="727bb-105">Windows Server 2008 R2에서 IIS 버전 7.5를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-105">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="727bb-106">**서버 관리자** 에서 역할을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="727bb-106">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="727bb-107">**역할 요약** 에서 **역할 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-107">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="727bb-108">**다음** 을 클릭 하 여 **서버 역할 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-108">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="727bb-109">**역할** 목록에서 **응용 프로그램 서버** 를 선택 하 고 **다음** 을 두 번 클릭 하 여 응용 프로그램 서버 역할에 대 한 **역할 서비스 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-109">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="727bb-110">**웹 서버 (IIS)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-110">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="727bb-111">추가 역할 서비스 및 기능을 설치 하 라는 메시지가 표시 되 면 **필요한 기능 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-111">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="727bb-112">**다음** 을 두 번 클릭 하 여 웹 서버 (IIS) 역할에 대 한 **역할 서비스 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-112">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="727bb-113">**관리 도구** 를 확장 한 다음 **IIS 6 관리 호환성** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-113">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="727bb-114">**IIS 6 스크립팅 도구** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-114">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="727bb-115">추가 역할 서비스 및 기능을 설치 하 라는 메시지가 표시 되 면 **필요한 역할 서비스 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-115">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="727bb-116">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-116">Click **Next**.</span></span>  
  
6. <span data-ttu-id="727bb-117">선택 항목 요약이 올바르면 **설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-117">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="727bb-118">설치가 완료 되 면 **닫기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-118">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="727bb-119">Windows 7에서 IIS 버전 7.5를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-119">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="727bb-120">**시작** 을 클릭하고 **제어판** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-120">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="727bb-121">**프로그램** 그룹을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-121">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="727bb-122">**프로그램 및 기능** 에서 **Windows 기능 사용/사용 안 함** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-122">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="727bb-123">**사용자 계정 컨트롤** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-123">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="727bb-124">**Continue(계속)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-124">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="727bb-125">**Windows 기능** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-125">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="727bb-126">**인터넷 정보 서비스** 레이블이 지정 된 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-126">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="727bb-127">**서비스 World Wide Web** 레이블이 지정 된 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-127">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="727bb-128">**응용 프로그램 개발 기능** 이라는 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-128">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="727bb-129">다음 항목이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-129">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="727bb-130">**.NET 확장성**</span><span class="sxs-lookup"><span data-stu-id="727bb-130">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="727bb-131">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="727bb-131">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="727bb-132">**ISAPI 확장**</span><span class="sxs-lookup"><span data-stu-id="727bb-132">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="727bb-133">**ISAPI 필터**</span><span class="sxs-lookup"><span data-stu-id="727bb-133">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="727bb-134">**World Wide Web Services** 레이블이 지정 된 항목 아래에서 **일반 Http 기능** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-134">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="727bb-135">**정적 콘텐츠** 가 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-135">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="727bb-136">**World Wide Web Services** 라는 항목에서 **보안** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-136">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="727bb-137">**Windows 인증** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-137">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="727bb-138">**인터넷 정보 서비스** 디렉터리에서 **웹 관리 도구** 레이블이 지정 된 항목을 확장 한 다음 **IIS 관리 콘솔** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-138">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="727bb-139">**Iis 6 관리 호환성** 이라는 레이블이 지정 된 항목을 확장 하 고 **Iis 6 스크립팅 도구** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-139">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="727bb-140">**인터넷 정보 서비스** 디렉터리에서 **Microsoft .NET Framework 3.5.1** 이라는 레이블이 지정 된 항목을 확장 하 고 **Windows Communication Foundation Http 활성화** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-140">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="727bb-141">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-141">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="727bb-142">Windows Server 2008에서 IIS 버전 7.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-142">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="727bb-143">**서버 관리자** 에서 **역할** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-143">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="727bb-144">**역할 요약** 에서 **역할 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-144">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="727bb-145">**다음** 을 클릭 하 여 **서버 역할 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-145">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="727bb-146">**역할** 목록에서 **응용 프로그램 서버** 를 선택 하 고 **다음** 을 두 번 클릭 하 여 응용 프로그램 서버 역할에 대 한 **역할 서비스 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-146">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="727bb-147">**웹 서버 (IIS)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-147">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="727bb-148">추가 역할 서비스 및 기능을 설치 하 라는 메시지가 표시 되 면 **필요한 기능 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-148">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="727bb-149">**다음** 을 두 번 클릭 하 여 웹 서버 (IIS) 역할에 대 한 **역할 서비스 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-149">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="727bb-150">**관리 도구** 를 확장 한 다음 **IIS 6 관리 호환성** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-150">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="727bb-151">**IIS 6 스크립팅 도구** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-151">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="727bb-152">추가 역할 서비스 및 기능을 설치 하 라는 메시지가 표시 되 면 **필요한 역할 서비스 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-152">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="727bb-153">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-153">Click **Next**.</span></span>  
  
6. <span data-ttu-id="727bb-154">선택 항목 요약이 올바르면 **설치** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-154">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="727bb-155">설치가 완료 되 면 **닫기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-155">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="727bb-156">Windows Vista에서 IIS 버전 7.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-156">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="727bb-157">시작을 클릭한 다음 제어판을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-157">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="727bb-158">**프로그램** 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-158">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="727bb-159">**프로그램 및 기능** 에서 **Windows 기능 사용/사용 안 함** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-159">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="727bb-160">**사용자 계정 컨트롤** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-160">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="727bb-161">**Continue(계속)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-161">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="727bb-162">**Windows 기능** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-162">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="727bb-163">**인터넷 정보 서비스** 레이블이 지정 된 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-163">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="727bb-164">**서비스 World Wide Web** 레이블이 지정 된 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-164">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="727bb-165">**응용 프로그램 개발 기능** 이라는 항목을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-165">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="727bb-166">다음 항목이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-166">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="727bb-167">**.NET 확장성**</span><span class="sxs-lookup"><span data-stu-id="727bb-167">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="727bb-168">**ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="727bb-168">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="727bb-169">**ISAPI 확장**</span><span class="sxs-lookup"><span data-stu-id="727bb-169">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="727bb-170">**ISAPI 필터**</span><span class="sxs-lookup"><span data-stu-id="727bb-170">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="727bb-171">**웹 관리 도구** 레이블이 지정 된 항목을 확장 한 다음 **IIS 관리 콘솔** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-171">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="727bb-172">**World Wide Web Services** 레이블이 지정 된 항목 아래에서 **일반 Http 기능** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-172">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="727bb-173">**정적 콘텐츠** 가 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-173">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="727bb-174">**World Wide Web Services** 라는 항목에서 **보안** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-174">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="727bb-175">**Windows 인증** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-175">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="727bb-176">**Iis 6 관리 호환성** 이라는 레이블이 지정 된 항목을 확장 하 고 **Iis 6 스크립팅 도구** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-176">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="727bb-177">**Microsoft .NET Framework 3.0** 이라는 레이블이 지정 된 항목을 확장 한 다음 **Windows Communication Foundation Http 활성화** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-177">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="727bb-178">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-178">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="727bb-179">Windows Server 2003에서 IIS 버전 6.0을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-179">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="727bb-180">**서버 관리** 에서 **역할 추가/제거** 를 클릭 한 후 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-180">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="727bb-181">**서버 역할** 목록에서 **응용 프로그램 서버 (IIS, ASP.NET)** 를 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-181">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="727bb-182">**ASP.NET 사용** 확인란을 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-182">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="727bb-183">선택 항목에 대한 요약이 모두 올바르면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-183">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="727bb-184">Windows XP 서비스 팩 2 및 서비스 팩 3에서 IIS 버전 5.1을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-184">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="727bb-185">제어판에서 **프로그램 추가/제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-185">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="727bb-186">**프로그램 추가/제거** 대화 상자에서 **Windows 구성 요소 추가/제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-186">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="727bb-187">**Windows 구성 요소 마법사** 에서 **인터넷 정보 서비스 (IIS)** 확인란을 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-187">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="727bb-188">**필요한 파일** 대화 상자가 표시 되 면 운영 체제 설치 디스크를 삽입 하 고 i386 폴더로 이동한 다음 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-188">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="727bb-189">설치가 완료 되 면 **마침** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-189">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="727bb-190">**프로그램 추가/제거** 대화 상자를 닫은 후 **제어판** 을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-190">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="727bb-191">IIS 및 ASP.NET의 설치를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="727bb-191">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="727bb-192">이 항목의 끝에 있는 HTML 파일을 루트 \InetPub\wwwroot 디렉터리에 저장하고 이름을 Default.aspx로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-192">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="727bb-193">브라우저 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-193">Open a browser window.</span></span>  
  
3. <span data-ttu-id="727bb-194">`http://localhost/Default.aspx`주소 상자에를 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-194">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="727bb-195">"Hello World"라는 텍스트가 포함된 웹 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-195">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="727bb-196">.NET Framework의 새 버전을 설치할 때마다 IIS의 웹 서비스 확장으로 aspnet_isapi를 다시 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-196">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="727bb-197">이렇게 하려면 `aspnet_regiis –I –enable` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="727bb-197">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="727bb-198">샘플 코드</span><span class="sxs-lookup"><span data-stu-id="727bb-198">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
