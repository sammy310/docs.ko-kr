---
description: '자세한 정보: 가상 디렉터리 설치 지침'
title: 가상 디렉터리 설치 지침
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 4b1a68fb657a59e9858c6efa7931c5d106231605
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755709"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="a98b0-103">가상 디렉터리 설치 지침</span><span class="sxs-lookup"><span data-stu-id="a98b0-103">Virtual Directory Setup Instructions</span></span>

<span data-ttu-id="a98b0-104">WCF (Windows Communication Foundation) 샘플 은%SystemDrive%\inetpub\wwwroot\servicemodelsamples 폴더에 매핑되는 servicemodelsamples 라는 공용 가상 디렉터리를 공유 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-104">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a98b0-105">%SystemDrive%는 일반적으로 C: 또는 D:이며 IIS(인터넷 정보 서비스)가 설치된 드라이브 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-105">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="a98b0-106">[Windows Communication Foundation 샘플에 대 한](one-time-setup-procedure-for-the-wcf-samples.md) Setupvroot.bat 및 Cleanupvroot.bat 파일을 실행 하 여 가상 디렉터리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-106">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="a98b0-107">가상 디렉터리를 수동으로 만들려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-107">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a98b0-108">프로시저</span><span class="sxs-lookup"><span data-stu-id="a98b0-108">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="a98b0-109">IIS 7.0 또는 7.5에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-109">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="a98b0-110">**시작** 메뉴에서 **실행** 을 클릭 한 다음 **inetmgr** 을 입력 하 여 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-110">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="a98b0-111">왼쪽 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 **사이트** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-111">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="a98b0-112">**기본 웹 사이트** 를 마우스 오른쪽 단추로 클릭 한 다음 **응용 프로그램 추가** 를 선택 하 여 **응용 프로그램 추가 창을** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-112">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="a98b0-113">창에서, `servicemodelsamples` 만들고 있는 가상 디렉터리의 별칭으로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-113">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="a98b0-114">%SystemDrive%\inetpub\wwwroot\servicemodelsamples 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-114">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="a98b0-115">실제 경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-115">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="a98b0-116">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-116">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="a98b0-117">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-117">Click **OK**.</span></span> <span data-ttu-id="a98b0-118">WCF 샘플에 웹 애플리케이션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-118">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a98b0-119">모든 WCF 샘플은 동일한 servicemodelsamples 웹 응용 프로그램을 사용 하므로이 작업은 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-119">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a98b0-120">이 문서에서는 `virtual directory`라는 용어는 `Web application`과 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-120">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="a98b0-121">가상 디렉터리를 만드는 것 외에도 해당 속성을 설정 하 여 WCF 서비스를 실행할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-121">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="a98b0-122">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a98b0-122">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="a98b0-123">IIS 5.1 또는 6.0에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-123">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="a98b0-124">명령 프롬프트 창을 열고를 입력 `start inetmgr` 하 여 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-124">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="a98b0-125">왼쪽 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 **웹 사이트** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-125">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="a98b0-126">**기본 웹 사이트** 를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기, 가상 디렉터리** 를 선택 하 여 가상 디렉터리 만들기 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-126">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="a98b0-127">마법사에서 `servicemodelsamples` 만들고 있는 가상 디렉터리의 별칭으로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-127">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="a98b0-128">경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-128">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="a98b0-129">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-129">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="a98b0-130">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-130">Click **Next**.</span></span>  
  
7. <span data-ttu-id="a98b0-131">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-131">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="a98b0-132">**읽기**</span><span class="sxs-lookup"><span data-stu-id="a98b0-132">**Read**</span></span>  
  
    - <span data-ttu-id="a98b0-133">**스크립트 실행(예: ASP)**</span><span class="sxs-lookup"><span data-stu-id="a98b0-133">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="a98b0-134">**다음** 을 클릭 한 다음 **마침** 을 클릭 하 여 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-134">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a98b0-135">모든 WCF 샘플에서 동일한 servicemodelsamples 가상 디렉터리를 사용 하므로이 작업은 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-135">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="a98b0-136">IIS 7.0 또는 7.5에서 추가 가상 디렉터리 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-136">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="a98b0-137">servicemodelsamples 노드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-137">Click the servicemodelsamples node.</span></span> <span data-ttu-id="a98b0-138">창 아래쪽에 두 개의 뷰가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-138">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="a98b0-139">아직 선택 하지 않은 경우 **기능 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-139">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="a98b0-140">**디렉터리 검색** 에 대 한 항목을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-140">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="a98b0-141">작업 창에서 **사용** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-141">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="a98b0-142">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-142">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="a98b0-143">마지막으로 다른 사용자가 액세스할 수 있도록 servicemodelsamples 폴더의 보안 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-143">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="a98b0-144">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a98b0-144">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="a98b0-145">IIS 5.1 또는 6.0에서 추가 가상 디렉터리 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-145">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="a98b0-146">Servicemodelsamples 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-146">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="a98b0-147">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-147">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="a98b0-148">**읽기**</span><span class="sxs-lookup"><span data-stu-id="a98b0-148">**Read**</span></span>  
  
    - <span data-ttu-id="a98b0-149">**방문 기록**</span><span class="sxs-lookup"><span data-stu-id="a98b0-149">**Log visits**</span></span>  
  
    - <span data-ttu-id="a98b0-150">**이 리소스 인덱싱**</span><span class="sxs-lookup"><span data-stu-id="a98b0-150">**Index this resource**</span></span>  
  
3. <span data-ttu-id="a98b0-151">**디렉터리 검색** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-151">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="a98b0-152">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-152">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="a98b0-153">IIS 7.0 또는 7.5에서 폴더의 보안 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-153">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="a98b0-154">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-154">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="a98b0-155">Servicemodelsamples 폴더를 마우스 오른쪽 단추로 클릭 하 고 **공유** 또는 **공유를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-155">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="a98b0-156">**추가** 단추의 왼쪽에 있는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-156">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="a98b0-157">**찾기** 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-157">Select the **Find** entry.</span></span> <span data-ttu-id="a98b0-158">**사용자 또는 그룹 선택** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-158">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="a98b0-159">**고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-159">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="a98b0-160">**위치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-160">Click **Locations**.</span></span> <span data-ttu-id="a98b0-161">이제 **위치** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-161">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="a98b0-162">사용 중인 컴퓨터에 대한 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-162">Select the entry for the computer being used.</span></span> <span data-ttu-id="a98b0-163">표시되어 있는 도메인이나 네트워크에 대한 항목이 아닌 로컬 컴퓨터를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-163">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="a98b0-164">컴퓨터를 선택한 후 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-164">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="a98b0-165">**지금 찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-165">Click **Find Now**.</span></span> <span data-ttu-id="a98b0-166">그러면 검색 결과가 로컬 컴퓨터와 연결된 개체로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-166">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="a98b0-167">**이름 (상대 고유 이름)** 열에서 **IIS_IUSRS** 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-167">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="a98b0-168">해당 항목을 선택 하 고 **확인** 을 클릭 하 여 검색 결과 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-168">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="a98b0-169">**확인** 을 클릭 하 여 **사용자 또는 그룹 선택** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-169">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="a98b0-170">**공유** 를 클릭 하 여 변경 내용을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-170">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="a98b0-171">공유 사용에 대 한 변경 내용이 완료 되 면 **완료** 를 클릭 하 여 **파일 공유** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-171">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="a98b0-172">IIS 5.1 또는 6.0에서 폴더의 보안 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a98b0-172">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="a98b0-173">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-173">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="a98b0-174">**Servicemodelsamples** 폴더를 마우스 오른쪽 단추로 클릭 한 다음 **공유 및 보안을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a98b0-174">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="a98b0-175">**보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-175">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="a98b0-176">IIS 6.0를 사용 하는 경우 **그룹 또는 사용자 이름** 상자에 **인터넷 게스트 계정** 이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-176">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="a98b0-177">배포 데이터베이스가 목록에 없는 경우 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="a98b0-177">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="a98b0-178">**시작** 을 클릭한 다음, **제어판** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-178">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="a98b0-179">**사용자 계정** 아이콘이 표시 되지 않으면 **종류별 보기로 전환을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-179">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="a98b0-180">**사용자 계정** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-180">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="a98b0-181">"제어판 아이콘을 선택 하십시오."에서 **사용자 계정** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-181">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="a98b0-182">**사용자 계정** 대화 상자에서 **고급** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-182">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="a98b0-183">**고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-183">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="a98b0-184">**로컬 사용자 및 그룹** 대화 상자에서 **사용자** 폴더를 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-184">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="a98b0-185">오른쪽 창에서 **인터넷 게스트 계정** 을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-185">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="a98b0-186">**속성** 대화 상자에서 인터넷 게스트 계정으로 사용 되는 이름을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-186">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="a98b0-187">기본적으로 이름은 "USR_" 다음에 컴퓨터의 이름이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-187">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="a98b0-188">**속성** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-188">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="a98b0-189">**로컬 사용자 및 그룹** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-189">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="a98b0-190">**사용자 계정** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-190">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="a98b0-191">기타 **사용자 계정** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-191">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="a98b0-192">**Servicemodelsamples 속성** 대화 상자의 **보안** 탭에서 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-192">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="a98b0-193">컴퓨터 이름 뒤에 백슬래시를 입력 한 다음 인터넷 사용자 계정 이름 (예: myMachineName% InternetGuestAccountName%)을 붙여 넣습니다. \\</span><span class="sxs-lookup"><span data-stu-id="a98b0-193">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="a98b0-194">**이름 확인** 을 클릭 하 여 추가를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-194">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="a98b0-195">이름이 올바른 경우 모두 밑줄이 있는 대문자입니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-195">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="a98b0-196">IIS 6.0의 경우 **그룹 또는 사용자 이름** 상자에도 NETWORK SERVICE가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-196">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="a98b0-197">NETWORK SERVICE가 표시되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="a98b0-197">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="a98b0-198">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-198">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="a98b0-199">**사용자 또는 그룹 선택** 대화 상자에서 컴퓨터 이름, 백슬래시를 차례로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-199">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="a98b0-200">백슬래시 뒤에 **service** 를 입력 합니다 (공백 없음).</span><span class="sxs-lookup"><span data-stu-id="a98b0-200">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="a98b0-201">**이름 확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-201">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="a98b0-202">여러 이름을 찾은 경우 **네트워크 서비스** 를 선택 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-202">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="a98b0-203">**확인** 을 클릭 하 여 **사용자 또는 그룹 선택** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-203">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="a98b0-204">IIS 5.1에서 Windows XP s p 2를 사용 하는 경우 **그룹 또는 사용자 이름** 상자에 인터넷 게스트 계정과 ASPNET이 모두 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-204">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="a98b0-205">ASPNET 사용자는 기본 제공 **사용자** 보안 그룹의 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-205">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="a98b0-206">이 경우 **사용자** 그룹이 대화 상자에 표시 되는 경우 허용 된 사용자 목록에 별도의 항목으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-206">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="a98b0-207">ASPNET이 **Users** 보안 그룹의 일부 인지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-207">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="a98b0-208">**시작** 메뉴에서 **제어판** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-208">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="a98b0-209">**사용자 계정** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-209">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="a98b0-210">**그룹** 열에서 **ASPNET** 의 값이 "사용자" 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98b0-210">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a98b0-211">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a98b0-211">See also</span></span>

- [<span data-ttu-id="a98b0-212">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="a98b0-212">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)
