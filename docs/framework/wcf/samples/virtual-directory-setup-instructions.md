---
title: 가상 디렉터리 설치 지침
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: dba6547888935ccf36ec0924fd3c95e8fbda5688
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243653"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="1999b-102">가상 디렉터리 설치 지침</span><span class="sxs-lookup"><span data-stu-id="1999b-102">Virtual Directory Setup Instructions</span></span>

<span data-ttu-id="1999b-103">WCF (Windows Communication Foundation) 샘플 은%SystemDrive%\inetpub\wwwroot\servicemodelsamples 폴더에 매핑되는 servicemodelsamples 라는 공용 가상 디렉터리를 공유 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1999b-104">%SystemDrive%는 일반적으로 C: 또는 D:이며 IIS(인터넷 정보 서비스)가 설치된 드라이브 위치에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="1999b-105">[Windows Communication Foundation 샘플에 대 한](one-time-setup-procedure-for-the-wcf-samples.md) Setupvroot.bat 및 Cleanupvroot.bat 파일을 실행 하 여 가상 디렉터리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="1999b-106">가상 디렉터리를 수동으로 만들려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="1999b-107">프로시저</span><span class="sxs-lookup"><span data-stu-id="1999b-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="1999b-108">IIS 7.0 또는 7.5에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1999b-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="1999b-109">**시작** 메뉴에서 **실행** 을 클릭 한 다음 **inetmgr** 을 입력 하 여 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="1999b-110">왼쪽 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 **사이트** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="1999b-111">**기본 웹 사이트** 를 마우스 오른쪽 단추로 클릭 한 다음 **응용 프로그램 추가** 를 선택 하 여 **응용 프로그램 추가 창을** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="1999b-112">창에서, `servicemodelsamples` 만들고 있는 가상 디렉터리의 별칭으로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="1999b-113">%SystemDrive%\inetpub\wwwroot\servicemodelsamples 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="1999b-114">실제 경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="1999b-115">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="1999b-116">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-116">Click **OK**.</span></span> <span data-ttu-id="1999b-117">WCF 샘플에 웹 애플리케이션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1999b-118">모든 WCF 샘플은 동일한 servicemodelsamples 웹 응용 프로그램을 사용 하므로이 작업은 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1999b-119">이 문서에서는 `virtual directory`라는 용어는 `Web application`과 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="1999b-120">가상 디렉터리를 만드는 것 외에도 해당 속성을 설정 하 여 WCF 서비스를 실행할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="1999b-121">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1999b-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="1999b-122">IIS 5.1 또는 6.0에서 가상 디렉터리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1999b-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="1999b-123">명령 프롬프트 창을 열고를 입력 `start inetmgr` 하 여 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="1999b-124">왼쪽 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 **웹 사이트** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="1999b-125">**기본 웹 사이트** 를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기, 가상 디렉터리** 를 선택 하 여 가상 디렉터리 만들기 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="1999b-126">마법사에서 `servicemodelsamples` 만들고 있는 가상 디렉터리의 별칭으로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="1999b-127">경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="1999b-128">대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="1999b-129">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="1999b-130">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="1999b-131">**읽기**</span><span class="sxs-lookup"><span data-stu-id="1999b-131">**Read**</span></span>  
  
    - <span data-ttu-id="1999b-132">**스크립트 실행(예: ASP)**</span><span class="sxs-lookup"><span data-stu-id="1999b-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="1999b-133">**다음** 을 클릭 한 다음 **마침** 을 클릭 하 여 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1999b-134">모든 WCF 샘플에서 동일한 servicemodelsamples 가상 디렉터리를 사용 하므로이 작업은 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="1999b-135">IIS 7.0 또는 7.5에서 추가 가상 디렉터리 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1999b-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="1999b-136">servicemodelsamples 노드를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="1999b-137">창 아래쪽에 두 개의 뷰가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="1999b-138">아직 선택 하지 않은 경우 **기능 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="1999b-139">**디렉터리 검색** 에 대 한 항목을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="1999b-140">작업 창에서 **사용** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="1999b-141">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="1999b-142">마지막으로 다른 사용자가 액세스할 수 있도록 servicemodelsamples 폴더의 보안 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="1999b-143">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1999b-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="1999b-144">IIS 5.1 또는 6.0에서 추가 가상 디렉터리 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1999b-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="1999b-145">Servicemodelsamples 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="1999b-146">기본적으로 다음 확인란이 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="1999b-147">**읽기**</span><span class="sxs-lookup"><span data-stu-id="1999b-147">**Read**</span></span>  
  
    - <span data-ttu-id="1999b-148">**방문 기록**</span><span class="sxs-lookup"><span data-stu-id="1999b-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="1999b-149">**이 리소스 인덱싱**</span><span class="sxs-lookup"><span data-stu-id="1999b-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="1999b-150">**디렉터리 검색** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="1999b-151">이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="1999b-152">IIS 7.0 또는 7.5에서 폴더의 보안 속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1999b-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="1999b-153">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="1999b-154">Servicemodelsamples 폴더를 마우스 오른쪽 단추로 클릭 하 고 **공유** 또는 **공유를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="1999b-155">**추가** 단추의 왼쪽에 있는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="1999b-156">**찾기** 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-156">Select the **Find** entry.</span></span> <span data-ttu-id="1999b-157">**사용자 또는 그룹 선택** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="1999b-158">**고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="1999b-159">**위치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-159">Click **Locations**.</span></span> <span data-ttu-id="1999b-160">이제 **위치** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="1999b-161">사용 중인 컴퓨터에 대한 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="1999b-162">표시되어 있는 도메인이나 네트워크에 대한 항목이 아닌 로컬 컴퓨터를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="1999b-163">컴퓨터를 선택한 후 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="1999b-164">**지금 찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-164">Click **Find Now**.</span></span> <span data-ttu-id="1999b-165">그러면 검색 결과가 로컬 컴퓨터와 연결된 개체로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="1999b-166">**이름 (상대 고유 이름)** 열에서 **IIS_IUSRS** 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="1999b-167">해당 항목을 선택 하 고 **확인** 을 클릭 하 여 검색 결과 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="1999b-168">**확인** 을 클릭 하 여 **사용자 또는 그룹 선택** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="1999b-169">**공유** 를 클릭 하 여 변경 내용을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="1999b-170">공유 사용에 대 한 변경 내용이 완료 되 면 **완료** 를 클릭 하 여 **파일 공유** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="1999b-171">IIS 5.1 또는 6.0에서 폴더의 보안 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1999b-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="1999b-172">%SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="1999b-173">**Servicemodelsamples** 폴더를 마우스 오른쪽 단추로 클릭 한 다음 **공유 및 보안을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1999b-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="1999b-174">**보안** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="1999b-175">IIS 6.0를 사용 하는 경우 **그룹 또는 사용자 이름** 상자에 **인터넷 게스트 계정** 이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="1999b-176">배포 데이터베이스가 목록에 없는 경우 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="1999b-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="1999b-177">**시작** 을 클릭한 다음, **제어판** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="1999b-178">**사용자 계정** 아이콘이 표시 되지 않으면 **종류별 보기로 전환을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="1999b-179">**사용자 계정** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="1999b-180">"제어판 아이콘을 선택 하십시오."에서 **사용자 계정** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="1999b-181">**사용자 계정** 대화 상자에서 **고급** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="1999b-182">**고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="1999b-183">**로컬 사용자 및 그룹** 대화 상자에서 **사용자** 폴더를 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="1999b-184">오른쪽 창에서 **인터넷 게스트 계정** 을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="1999b-185">**속성** 대화 상자에서 인터넷 게스트 계정으로 사용 되는 이름을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="1999b-186">기본적으로 이름은 "USR_" 다음에 컴퓨터의 이름이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="1999b-187">**속성** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="1999b-188">**로컬 사용자 및 그룹** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="1999b-189">**사용자 계정** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="1999b-190">기타 **사용자 계정** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="1999b-191">**Servicemodelsamples 속성** 대화 상자의 **보안** 탭에서 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="1999b-192">컴퓨터 이름 뒤에 백슬래시를 입력 한 다음 인터넷 사용자 계정 이름 (예: myMachineName% InternetGuestAccountName%)을 붙여 넣습니다. \\</span><span class="sxs-lookup"><span data-stu-id="1999b-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="1999b-193">**이름 확인** 을 클릭 하 여 추가를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="1999b-194">이름이 올바른 경우 모두 밑줄이 있는 대문자입니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="1999b-195">IIS 6.0의 경우 **그룹 또는 사용자 이름** 상자에도 NETWORK SERVICE가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="1999b-196">NETWORK SERVICE가 표시되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="1999b-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="1999b-197">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="1999b-198">**사용자 또는 그룹 선택** 대화 상자에서 컴퓨터 이름, 백슬래시를 차례로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="1999b-199">백슬래시 뒤에 **service** 를 입력 합니다 (공백 없음).</span><span class="sxs-lookup"><span data-stu-id="1999b-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="1999b-200">**이름 확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="1999b-201">여러 이름을 찾은 경우 **네트워크 서비스** 를 선택 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="1999b-202">**확인** 을 클릭 하 여 **사용자 또는 그룹 선택** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="1999b-203">IIS 5.1에서 Windows XP s p 2를 사용 하는 경우 **그룹 또는 사용자 이름** 상자에 인터넷 게스트 계정과 ASPNET이 모두 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="1999b-204">ASPNET 사용자는 기본 제공 **사용자** 보안 그룹의 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="1999b-205">이 경우 **사용자** 그룹이 대화 상자에 표시 되는 경우 허용 된 사용자 목록에 별도의 항목으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="1999b-206">ASPNET이 **Users** 보안 그룹의 일부 인지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="1999b-207">**시작** 메뉴에서 **제어판** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="1999b-208">**사용자 계정** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="1999b-209">**그룹** 열에서 **ASPNET** 의 값이 "사용자" 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1999b-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1999b-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1999b-210">See also</span></span>

- [<span data-ttu-id="1999b-211">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="1999b-211">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)
