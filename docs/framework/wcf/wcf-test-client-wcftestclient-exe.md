---
title: WCF 테스트 클라이언트(WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: ac89b234dfafe3f87f1423a04ce8e4dd6b44b991
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321184"
---
# <a name="wcf-test-client-wcftestclientexe"></a><span data-ttu-id="96257-102">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="96257-102">WCF Test Client (WcfTestClient.exe)</span></span>
<span data-ttu-id="96257-103">WCF (Windows Communication Foundation) 테스트 클라이언트 (Wcftestclient.exe)는 사용자가 테스트 매개 변수를 입력 하 고, 해당 입력을 서비스에 제출 하 고, 서비스가 다시 전송 하는 응답을 볼 수 있는 GUI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="96257-103">Windows Communication Foundation (WCF) Test Client (WcfTestClient.exe) is a GUI tool that enables users to input test parameters, submit that input to the service, and view the response that the service sends back.</span></span> <span data-ttu-id="96257-104">WCF 서비스 호스트와 결합 될 때 원활한 서비스 테스트 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-104">It provides a seamless service testing experience when combined with WCF Service Host.</span></span>

<span data-ttu-id="96257-105">일반적으로 WCF 테스트 클라이언트 (Wcftestclient.exe)는 다음 위치에서 찾을 수 있습니다. `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE`-Community는 설치 된 Visual Studio의 수준에 따라 "Enterprise", "Professional" 또는 "Community" 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-105">You can typically find the WCF Test Client (WcfTestClient.exe) in the following location: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` - Community may be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed.</span></span>

## <a name="scenarios-for-using-test-client"></a><span data-ttu-id="96257-106">테스트 클라이언트 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="96257-106">Scenarios for Using Test Client</span></span>

<span data-ttu-id="96257-107">다음 섹션에서는 WCF 테스트 클라이언트를 사용 하 여 개발 프로세스를 간소화할 수 있는 가장 일반적인 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-107">The following sections discuss the most common scenarios in which you can use WCF Test Client to streamline your development process.</span></span>

### <a name="inside-visual-studio"></a><span data-ttu-id="96257-108">Visual Studio의 경우</span><span class="sxs-lookup"><span data-stu-id="96257-108">Inside Visual Studio</span></span>

#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a><span data-ttu-id="96257-109">WCF 서비스 호스트가 단일 서비스에서 WCF 테스트 클라이언트 시작</span><span class="sxs-lookup"><span data-stu-id="96257-109">WCF Service Host Starts WCF Test Client with a Single Service</span></span>

<span data-ttu-id="96257-110">새 WCF 서비스 프로젝트를 만들고 F5 키를 눌러 디버거를 시작 하면 WCF 서비스 호스트가 프로젝트에서 서비스를 호스트 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-110">After you create a new WCF service project and press F5 to start the debugger, the WCF Service Host begins to host the service in your project.</span></span> <span data-ttu-id="96257-111">그런 다음 WCF Test Client가 열리고 구성 파일에 정의 된 서비스 끝점의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-111">Then, WCF Test Client opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="96257-112">그러면 매개 변수를 테스트하고, 서비스를 호출하며, 이 프로세스를 반복하여 테스트를 계속하고 서비스의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-112">You can test the parameters and invoke the service, and repeat this process to continuously test and validate your service.</span></span>

#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a><span data-ttu-id="96257-113">WCF 서비스 호스트가 여러 서비스에서 WCF 테스트 클라이언트 시작</span><span class="sxs-lookup"><span data-stu-id="96257-113">WCF Service Host Starts WCF Test Client with Multiple Services</span></span>

<span data-ttu-id="96257-114">WCF 테스트 클라이언트를 사용 하 여 여러 서비스를 포함 하는 서비스 프로젝트를 디버그할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-114">You can also use WCF Test Client to help debug a service project that contains multiple services.</span></span> <span data-ttu-id="96257-115">WCF 테스트 클라이언트가 열리면 프로젝트의 서비스 목록을 자동으로 반복 하 여 테스트를 위해 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96257-115">When WCF Test Client opens, it automatically iterates the list of services in your project and opens them for testing.</span></span>

### <a name="outside-visual-studio"></a><span data-ttu-id="96257-116">Visual Studio 외부</span><span class="sxs-lookup"><span data-stu-id="96257-116">Outside Visual Studio</span></span>

<span data-ttu-id="96257-117">Visual Studio 외부에서 WCF 테스트 클라이언트 (Wcftestclient.exe)를 호출 하 여 인터넷에서 임의의 서비스를 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-117">You can also invoke the WCF Test Client (WcfTestClient.exe) outside Visual Studio to test an arbitrary service on the Internet.</span></span> <span data-ttu-id="96257-118">도구를 찾으려면 다음 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-118">To locate the tool, go to the following location:</span></span>

<span data-ttu-id="96257-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (여기서 community는 컴퓨터에 설치 된 Visual Studio의 수준에 따라 "엔터프라이즈", "전문가" 또는 "커뮤니티" 중 하나일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="96257-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (where community can be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed on the machine)</span></span>

<span data-ttu-id="96257-120">도구를 사용하려면 파일 이름을 두 번 클릭하여 이 위치에서 열거나 명령줄에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-120">To use the tool, double-click the file name to open it from this location, or launch it from a command line.</span></span>

<span data-ttu-id="96257-121">WCF 테스트 클라이언트는 명령줄 인수로 임의의 개수의 Uri를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-121">WCF Test Client takes an arbitrary number of URIs as command line arguments.</span></span>  <span data-ttu-id="96257-122">이들은 테스트할 수 있는 서비스의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="96257-122">These are the URIs of services that can be tested.</span></span>

`wcfTestClient.exe URI1 URI2 …`

<span data-ttu-id="96257-123">WCF 테스트 클라이언트 창이 열리면 **파일** ->**서비스 추가**를 클릭 하 고 열려는 서비스의 끝점 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-123">After the WCF Test Client window is opened, click **File**->**Add Service**, and enter the endpoint address of the service you want to open.</span></span>

## <a name="wcf-test-client-user-interface"></a><span data-ttu-id="96257-124">WCF 테스트 클라이언트 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96257-124">WCF Test Client User Interface</span></span>

<span data-ttu-id="96257-125">WCF 테스트 클라이언트는 단일 서비스 또는 여러 서비스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-125">You can use WCF Test Client with a single service or multiple services.</span></span>

### <a name="service-operations"></a><span data-ttu-id="96257-126">서비스 작업</span><span class="sxs-lookup"><span data-stu-id="96257-126">Service Operations</span></span>

<span data-ttu-id="96257-127">WCF 테스트 클라이언트 주 창의 왼쪽 창에는 사용 가능한 모든 서비스와 해당 끝점 및 작업이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-127">The left pane of the WCF Test Client main window lists all the available services, along with their respective endpoints and operations.</span></span>

<span data-ttu-id="96257-128">작업을 두 번 클릭하면 작업 이름이 표시된 새 탭 내의 오른쪽 창에서 해당 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-128">When you double-click an operation, you can view its content in the right pane inside a new tab with the operation's name.</span></span>

<span data-ttu-id="96257-129">또한 왼쪽 창에는 클라이언트 구성 파일이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-129">The left pane also lists client configuration files.</span></span> <span data-ttu-id="96257-130">이 항목 중 하나를 두 번 클릭하면 오른쪽 창의 새 탭 창에 파일 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-130">Double-click any of the items to display the content of the file in a new tabbed window in the right pane.</span></span>

### <a name="entering-test-parameters"></a><span data-ttu-id="96257-131">테스트 매개 변수 입력</span><span class="sxs-lookup"><span data-stu-id="96257-131">Entering Test Parameters</span></span>

<span data-ttu-id="96257-132">테스트 매개 변수를 보려면 작업을 두 번 클릭하여 오른쪽 창에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96257-132">To view the test parameters, double-click an operation to open it in the right pane.</span></span> <span data-ttu-id="96257-133">매개 변수는 기본적으로 **서식이 지정** 된 보기에 표시 되며, 매개 변수에 대해 임의의 값을 입력 하 여 서비스를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-133">The parameters are showed in **Formatted** view by default, and you can enter arbitrary values for the parameters to test the service.</span></span>

<span data-ttu-id="96257-134">메시지의 XML을 보려면 **xml**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-134">To view the message's XML, click **XML**.</span></span> <span data-ttu-id="96257-135">이를 서비스로 보내려면 **호출**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-135">To send them to the service, click **Invoke**.</span></span>

<span data-ttu-id="96257-136">데이터 집합 매개 변수의 **경우 ...**</span><span class="sxs-lookup"><span data-stu-id="96257-136">For a DataSet parameter, click the **…**</span></span> <span data-ttu-id="96257-137">**편집** ... 옆의 단추</span><span class="sxs-lookup"><span data-stu-id="96257-137">button next to **Edit…**</span></span> <span data-ttu-id="96257-138">를 편집 하 여 DataGrid를 표시 하는 새 창에서 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-138">to edit it in a new window showing the DataGrid.</span></span> <span data-ttu-id="96257-139">**데이터 집합 복사** 및 **데이터 집합 붙여넣기** 단추의 모양을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-139">Notice the appearance of the **Copy DataSet** and **Paste DataSet** buttons.</span></span> <span data-ttu-id="96257-140">처음 편집할 때 DataSet 개체의 스키마를 알 수 없는 경우 DataGrid는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-140">If the schema of the DataSet object is unknown upon the first edit, the DataGrid is empty.</span></span> <span data-ttu-id="96257-141">DataSet 개체는 같은 스키마를 사용하여 DataGrid의 현재 개체에 붙여 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-141">You have to paste a DataSet object with the same schema into the current object in the DataGrid.</span></span> <span data-ttu-id="96257-142">(붙여넣기 작업 전에 다른 위치에서 스키마를 복사 해야 합니다.) **데이터 집합 복사** 단추를 클릭 하 여 나중에 사용 하기 위해 데이터 집합 개체를 복사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-142">(Notice that you need to copy the schema from somewhere else before the paste operation.) You can also copy a Dataset object for future usage by clicking the **Copy DataSet** button.</span></span>

<span data-ttu-id="96257-143">서비스의 응답은 테스트 매개 변수 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-143">The service's response appears below the test parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="96257-144">예상 반환 값이 문자열이면 제공된 입력 값이 따옴표 안에 들어 있지 않은 경우에도 결과는 따옴표로 묶인 문자열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-144">If the expected return value is a string, the result will be displayed as a quoted string even though the input provided was not in quotes.</span></span>

<span data-ttu-id="96257-145">서비스의 계약을 만들 때 특정 작업을 단방향으로 지정한 경우 서비스 응답이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-145">If you specified a particular operation as one-way when you created the contract for the service, no service response is displayed.</span></span> <span data-ttu-id="96257-146">메시지가 배달을 위해 대기 중이면 대화 상자가 표시되어 메시지를 보냈음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96257-146">As soon as the message is queued for delivery, a dialog box pops up to notify you that the message was successfully sent.</span></span>

### <a name="session-support"></a><span data-ttu-id="96257-147">세션 지원</span><span class="sxs-lookup"><span data-stu-id="96257-147">Session Support</span></span>

<span data-ttu-id="96257-148">서비스 작업의 탭에서 **새 프록시 시작** 확인란을 사용 하 여 세션 지원을 설정/해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-148">The **Start a new proxy** check box in a service operation's tab enables you to toggle session support.</span></span> <span data-ttu-id="96257-149">이 상자는 기본적으로 선택되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-149">This box is cleared by default.</span></span>

<span data-ttu-id="96257-150">특정 작업 (또는 동일한 서비스 끝점의 다른 작업)에 대 한 테스트 매개 변수를 입력 하 고 확인란의 선택을 취소 하 여 여러 번 **호출** 을 클릭 하는 경우 이러한 작업은 하나의 프록시를 공유 하 고 서비스 상태는 여러 개에서 지속 됩니다. 작업도.</span><span class="sxs-lookup"><span data-stu-id="96257-150">When you enter test parameters for a specific operation (or another operation in the same service endpoint) and click **Invoke** multiple times with the check box cleared, these operations share one proxy and the service status is persisted across multiple operations.</span></span>

<span data-ttu-id="96257-151">**새 프록시 시작** 확인란을 선택 하면 각 **호출**에 대해 새 프록시가 시작 되 고, 이전 세션 시나리오가 종료 되 고, 서비스 상태가 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-151">If the **Start a new proxy** check box is checked, a new proxy is started for each **Invoke**, the previous session scenario is ended, and the service status is reset.</span></span>

### <a name="editing-client-configuration"></a><span data-ttu-id="96257-152">클라이언트 구성 편집</span><span class="sxs-lookup"><span data-stu-id="96257-152">Editing Client Configuration</span></span>

<span data-ttu-id="96257-153">WCF 테스트 클라이언트 주 창의 왼쪽 창에는 클라이언트 구성 파일이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-153">The left pane of the WCF Test Client main window lists client configuration files.</span></span> <span data-ttu-id="96257-154">이 항목 중 하나를 두 번 클릭하면 오른쪽 창에 파일 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-154">Double-click any of the items to display the contents of the file in the right pane.</span></span>

#### <a name="edit-with-service-configuration-editor"></a><span data-ttu-id="96257-155">서비스 구성 편집기로 편집</span><span class="sxs-lookup"><span data-stu-id="96257-155">Edit with Service Configuration Editor</span></span>

<span data-ttu-id="96257-156">왼쪽 창에서 **구성 파일** 을 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴 **SvcConfigEditor를 사용 하 여 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-156">Right-click **Config File** in the left pane and select the context menu **Edit with SvcConfigEditor**.</span></span> <span data-ttu-id="96257-157">서비스 구성 편집기가 시작되어 클라이언트 구성 내용이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-157">Service Configuration Editor is launched with the client configuration content.</span></span> <span data-ttu-id="96257-158">이 도구 내에서 구성을 편집하고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-158">You can edit the configuration and save it within the tool.</span></span>

<span data-ttu-id="96257-159">서비스 구성 편집기에서 파일을 저장 한 후 WCF 테스트 클라이언트는 파일이 외부에서 수정 되었음을 알리는 경고 메시지를 표시 하 고 해당 파일을 다시 로드할지 여부를 묻는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-159">After saving the file in Service Configuration Editor, WCF Test Client displays a warning message to inform you that the file has been modified outside and asks whether you would like to reload it.</span></span>

<span data-ttu-id="96257-160">**예**를 선택 하면 "client.msi" 탭의 구성 콘텐츠가 편집기에서 변경한 내용을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-160">If you select **Yes**, the configuration content in the "Client.dll.config" tab reflects the changes you made in the editor.</span></span>

<span data-ttu-id="96257-161">**아니요**를 선택 하면 "client.msi" 탭의 구성 콘텐츠가 변경 되지 않은 상태로 유지 되 고 수정 된 내용이 원본 파일에 자동으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-161">If you select **No**, the configuration content in the "Client.dll.config" tab remains unchanged and the modified content is automatically saved to the source file.</span></span>

#### <a name="restore-to-default-configuration"></a><span data-ttu-id="96257-162">기본 구성으로 복원</span><span class="sxs-lookup"><span data-stu-id="96257-162">Restore to Default Configuration</span></span>

<span data-ttu-id="96257-163">모든 변경 내용을 취소 하 고 기본 클라이언트 구성으로 복원 하려면 왼쪽 창에서 **구성 파일** 을 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴 **기본 구성으로 복원**을 선택 합니다. 기본 구성 값이 로드 되 고 "client.msi" 탭의 내용이 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-163">If you want to cancel all the changes and restore to the default client configuration, right-click **Config File** in the left pane and select the context menu **Restore to Default Config**. The default configuration value is loaded and content in "Client.dll.config" tab is restored.</span></span>

#### <a name="validate-changes"></a><span data-ttu-id="96257-164">변경 내용 확인</span><span class="sxs-lookup"><span data-stu-id="96257-164">Validate Changes</span></span>

<span data-ttu-id="96257-165">WCF 테스트 클라이언트에 저장 된 변경 내용이 로드 되는 경우 WCF 스키마에 대 한 구성의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-165">When saved changes are being loaded in WCF Test Client, the configuration is checked for validity against WCF schema.</span></span> <span data-ttu-id="96257-166">오류가 발견되면 오류 정보를 보여 주는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-166">If errors are found, a dialog box is displayed to show error details.</span></span>

<span data-ttu-id="96257-167">프록시 생성, 이진 컴파일 또는 서비스 호출 중에는 편집을 지 원하는 메뉴 항목 (즉, "편집 ...", "복원 ..." 등)을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-167">During proxy generation, binary compiling, or service invoking, menu items that support editing (that is, "Edit …", "Restore …", and so on) are disabled.</span></span> <span data-ttu-id="96257-168">업데이트 된 구성을 WCF 테스트 클라이언트에 로드할 때도 서비스 호출을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-168">Service invocation is also disabled when loading updated configuration to WCF Test Client.</span></span>

#### <a name="persist-client-configuration"></a><span data-ttu-id="96257-169">클라이언트 구성 유지</span><span class="sxs-lookup"><span data-stu-id="96257-169">Persist Client Configuration</span></span>

<span data-ttu-id="96257-170">**도구** ->**옵션** ->**클라이언트 구성** 탭에는 기본적으로 사용 하도록 설정 된 서비스를 **시작할 때 항상 구성 다시 생성** 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-170">The **Tools**->**Options**->**Client Configuration** tab contains an **Always Regenerate Config When Launching Services** option, which is enabled by default.</span></span> <span data-ttu-id="96257-171">이 옵션은 WCF 테스트 클라이언트에서 서비스를 로드할 때마다 최신 서비스 계약 및 서비스 App.config 파일을 기반으로 구성 파일을 다시 생성 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-171">This option specifies that every time WCF Test Client loads a service, it regenerates a configuration file based on the latest service contract and service App.config files.</span></span>

<span data-ttu-id="96257-172">WCF 서비스에 대 한 클라이언트 구성을 편집 하 고 항상이 업데이트 된 파일을 사용 하 여 서비스를 디버깅 하려면 **다시 생성** 옵션을 선택 취소 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-172">If you have edited the client configuration for your WCF service and want to always use this updated file to debug your service, you can uncheck the **Regenerate** option.</span></span> <span data-ttu-id="96257-173">이렇게 하면 서비스를 업데이트 하 고 WCF 테스트 클라이언트를 다시 여는 경우에도 업데이트 된 서비스를 기반으로 하 여 다시 생성 되는 것이 아니라 이전에 업데이트 한 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-173">By doing so, even when you update the service and reopen WCF Test Client, the Client.dll.config file is the one you updated previously instead of a regenerated one based on the updated service.</span></span>

<span data-ttu-id="96257-174">그러나 다시 생성된 프록시와 일치하도록 구성 파일을 편집해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-174">However, you might need to edit the configuration file to make it consistent with the regenerated proxy.</span></span> <span data-ttu-id="96257-175">다시 생성된 프록시와 구성 파일이 업데이트된 서비스로 인해 일치하지 않으면 서비스를 호출할 때 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-175">If the regenerated proxy and configuration file are mismatched due to an updated service, errors will occur when the service is invoked.</span></span>

> [!CAUTION]
> <span data-ttu-id="96257-176">클라이언트 구성 파일을 수정한 후 나중에 다시 사용하기 위해 선택하는 경우 파일이 다음 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-176">If you have modified the client configuration file and select to reuse it in the future, you can find the file in the following location:</span></span>
>
> <span data-ttu-id="96257-177">\Documents 및 설정 \\ [사용자 계정] \My Documents\Test 클라이언트 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="96257-177">\Documents and Settings\\[User Account]\My Documents\Test Client Projects.</span></span>
>
> <span data-ttu-id="96257-178">클라이언트 구성 파일에 저장된 업데이트된 자격 증명 정보는 ACL(Access Control 목록)을 통해 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-178">Any updated credential information stored to the client configuration file is protected by the Access Control List (ACL) of this folder.</span></span>

### <a name="adding-removing-and-refreshing-services"></a><span data-ttu-id="96257-179">서비스 추가, 제거 및 새로 고침</span><span class="sxs-lookup"><span data-stu-id="96257-179">Adding, Removing and Refreshing Services</span></span>

#### <a name="add-service"></a><span data-ttu-id="96257-180">서비스 추가</span><span class="sxs-lookup"><span data-stu-id="96257-180">Add Service</span></span>

<span data-ttu-id="96257-181">**파일** ->**서비스 추가** 를 클릭 하 여 WCF 테스트 클라이언트에 서비스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-181">Click **File**->**Add Service** to add a service to WCF Test Client.</span></span> <span data-ttu-id="96257-182">그런 다음 추가할 서비스의 URI(엔드포인트 주소)를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-182">You are then required to type the URI (endpoint address) of the service to be added.</span></span> <span data-ttu-id="96257-183">서비스 주소는 mex 주소나 WSDL 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-183">The service’s address can be a mex address or WSDL address.</span></span>

<span data-ttu-id="96257-184">**최근 서비스** 하위 메뉴에서 최근에 추가 된 서비스의 10 개 목록을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-184">You can also find a list of 10 recently added services' endpoints in the **Recent Services** submenu.</span></span> <span data-ttu-id="96257-185">하나를 선택 하면 지정 된 서비스가 WCF 테스트 클라이언트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-185">If you select one of them, the specified service is added to WCF Test Client.</span></span>

<span data-ttu-id="96257-186">서비스 트리 **내 서비스 프로젝트**의 루트를 마우스 오른쪽 단추로 클릭 하 고 **서비스 추가** 를 선택 하 여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-186">You can also right-click the root of service tree **My Service Projects**, and select **Add Service** to achieve the same result.</span></span>

<span data-ttu-id="96257-187">프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 편집을 지원하는 메뉴 항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-187">During proxy generation, binary compiling, or service invocation, menu items that support adding a service are disabled.</span></span> <span data-ttu-id="96257-188">서비스 호출도 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-188">Service invocation is also disabled.</span></span>

#### <a name="remove-service"></a><span data-ttu-id="96257-189">서비스 제거</span><span class="sxs-lookup"><span data-stu-id="96257-189">Remove Service</span></span>

<span data-ttu-id="96257-190">제거할 서비스의 서비스 루트를 마우스 오른쪽 단추로 클릭 하 고 **서비스 제거** 를 선택 하 여 WCF 테스트 클라이언트에서 서비스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-190">Right-click the service root of the service to be removed, and select **Remove Service** to remove a service from WCF Test Client.</span></span>

<span data-ttu-id="96257-191">프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 제거를 지원하는 메뉴 항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-191">During proxy generation, binary compiling, or service invocation, menu items that support removing a service are disabled.</span></span> <span data-ttu-id="96257-192">서비스 호출도 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-192">Service invocation is also disabled.</span></span>

#### <a name="refresh-service"></a><span data-ttu-id="96257-193">서비스 새로 고침</span><span class="sxs-lookup"><span data-stu-id="96257-193">Refresh Service</span></span>

<span data-ttu-id="96257-194">WCF 테스트 클라이언트가 실행 되는 동안 서비스를 변경 하 고 해당 서비스에 대 한 WCF 테스트 클라이언트 구현이 최신 상태 인지 확인 하려면 서비스의 서비스 루트를 마우스 오른쪽 단추로 클릭 하 고 **서비스 새로 고침**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-194">If a change is made to the service while WCF Test Client is running and you want to ensure that the WCF Test Client implementation for that service is up-to-date, right-click the service root of the service, and select **Refresh Service**.</span></span> <span data-ttu-id="96257-195">서비스를 새로 고친 한 서비스 상태는 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-195">Note that after refreshing, the service status is reset.</span></span>

<span data-ttu-id="96257-196">프록시 생성, 이진 컴파일 또는 서비스 호출 도중에는 서비스 새로 고침을 지원하는 메뉴 항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-196">During proxy generation, binary compiling, or service invocation, menu items that support refreshing a service are disabled.</span></span> <span data-ttu-id="96257-197">서비스 호출도 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-197">Service invocation is also disabled.</span></span>

## <a name="location-of-files-generated-by-the-test-client"></a><span data-ttu-id="96257-198">테스트 클라이언트에서 생성한 파일의 위치</span><span class="sxs-lookup"><span data-stu-id="96257-198">Location of Files Generated by the Test Client</span></span>

<span data-ttu-id="96257-199">기본적으로 WCF 테스트 클라이언트는 생성 된 클라이언트 코드와 구성 파일을 "%Appdata%\local\temp\test client projects Client Projects" 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-199">By default, WCF Test Client stores generated client code and configuration files in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span> <span data-ttu-id="96257-200">이 폴더는 WCF 테스트 클라이언트가 종료 된 후 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-200">This folder is deleted after WCF Test Client exits.</span></span> <span data-ttu-id="96257-201">WCF 테스트 클라이언트에서 구성 파일이 수정 되 고 **서비스를 시작할 때 항상 구성 다시 생성** 옵션을 사용 하지 않도록 설정 하면 수정 된 파일이 매핑을 사용 하 여 "My Documents\Test Client Projects" 아래의 "cachedconfig" 폴더로 복사 됩니다. 메타 데이터-파일 이름-파일 이름) XML 파일을 인덱스로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-201">If a configuration file is modified in WCF Test Client and the **Always Regenerate Config When Launching Services** option is disabled, the modified file is copied to the "CachedConfig" folder under "My Documents\Test Client Projects" with a mapping (metadata-address-to-file-name) XML file as an index.</span></span>

<span data-ttu-id="96257-202">명령줄에서 WCF 테스트 클라이언트를 시작 하 고, `/ProjectPath` 스위치를 사용 하 여 생성 된 파일을 저장 하는 데 필요한 새 경로를 지정 하거나, `/RestoreProjectPath` 스위치를 사용 하 여 기본 위치를 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-202">You can also start WCF Test Client in a command line, use the `/ProjectPath` switch to specify a new desired path for storing generated files, or use the `/RestoreProjectPath` switch to restore the default location.</span></span> <span data-ttu-id="96257-203">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-203">The syntax is as follows:</span></span>

`wcfTestClient.exe /ProjectPath [desired location]`

<span data-ttu-id="96257-204">이 명령을 실행 해도 WCF 테스트 클라이언트는 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-204">Running this command does not open WCF Test Client.</span></span> <span data-ttu-id="96257-205">폴더 위치만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-205">Only the folder location is changed.</span></span> <span data-ttu-id="96257-206">WCF 테스트 클라이언트가 실행 중인지 여부에 관계 없이이 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-206">You can run this command whether WCF Test Client is running or not.</span></span> <span data-ttu-id="96257-207">WCF 테스트 클라이언트를 다시 시작할 때 새 위치가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-207">The new location is applied when WCF Test Client is restarted.</span></span> <span data-ttu-id="96257-208">위치 정보는 레지스트리 또는 "%Appdata%\local\temp\test client projects Client Projects" 폴더의 Wcftestclient.exe 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-208">The location information can be saved in registry, or in the WcfTestClient.exe.option file in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span>

## <a name="features-supported-by-wcf-test-client"></a><span data-ttu-id="96257-209">WCF 테스트 클라이언트에서 지원되는 기능</span><span class="sxs-lookup"><span data-stu-id="96257-209">Features supported by WCF Test Client</span></span>

<span data-ttu-id="96257-210">다음은 WCF 테스트 클라이언트에서 지원 되는 기능의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="96257-210">The following is a list of features supported by WCF Test Client:</span></span>

- <span data-ttu-id="96257-211">서비스 호출: 요청/응답 및 단방향 메시지.</span><span class="sxs-lookup"><span data-stu-id="96257-211">Service Invocation: Request/Response and One-way message.</span></span>

- <span data-ttu-id="96257-212">바인딩: Svcutil.exe에서 지원되는 모든 바인딩.</span><span class="sxs-lookup"><span data-stu-id="96257-212">Bindings: all bindings supported by Svcutil.exe.</span></span>

- <span data-ttu-id="96257-213">세션 제어</span><span class="sxs-lookup"><span data-stu-id="96257-213">Controlling Session.</span></span>

- <span data-ttu-id="96257-214">메시지 계약</span><span class="sxs-lookup"><span data-stu-id="96257-214">Message Contract.</span></span>

- <span data-ttu-id="96257-215">XML 직렬화</span><span class="sxs-lookup"><span data-stu-id="96257-215">XML serialization.</span></span>

<span data-ttu-id="96257-216">다음은 WCF 테스트 클라이언트에서 지원 되지 않는 기능 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="96257-216">The following is a list of features not supported by WCF Test Client:</span></span>

- <span data-ttu-id="96257-217">형식: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 형식(관련 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 특성 포함), <xref:System.Xml.Linq.XDocument> 및 <xref:System.Xml.Linq.XElement> 형식, ADO.NET <xref:System.Data.DataTable> 형식</span><span class="sxs-lookup"><span data-stu-id="96257-217">Types: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, types that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface, including the related <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> attribute, and the <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> types and the ADO.NET <xref:System.Data.DataTable> type.</span></span>

- <span data-ttu-id="96257-218">이중 계약</span><span class="sxs-lookup"><span data-stu-id="96257-218">Duplex contract.</span></span>

- <span data-ttu-id="96257-219">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="96257-219">Transaction.</span></span>

- <span data-ttu-id="96257-220">보안: CardSpace, 인증서 및 사용자 이름/암호.</span><span class="sxs-lookup"><span data-stu-id="96257-220">Security: CardSpace , Certificate, and Username/Password.</span></span>

- <span data-ttu-id="96257-221">바인딩: WSFederationbinding, 컨텍스트 바인딩 및 Https 바인딩, WebHttpbinding(Json 응답 메시지 지원)</span><span class="sxs-lookup"><span data-stu-id="96257-221">Bindings: WSFederationbinding, any Context bindings and Https binding, WebHttpbinding (Json response message support).</span></span>

## <a name="closing-wcf-test-client"></a><span data-ttu-id="96257-222">WCF 테스트 클라이언트 닫기</span><span class="sxs-lookup"><span data-stu-id="96257-222">Closing WCF Test Client</span></span>

<span data-ttu-id="96257-223">다음과 같은 방법으로 WCF 테스트 클라이언트를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96257-223">You can close WCF Test Client in the following ways:</span></span>

- <span data-ttu-id="96257-224">**파일** 메뉴에서 **끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-224">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="96257-225">또는 WCF 테스트 클라이언트 주 창에서 **닫기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-225">Alternatively, in the WCF Test Client main window, click **Close**.</span></span> <span data-ttu-id="96257-226">이러한 작업은 모두 WCF 서비스 자동 호스트를 종료 하 고 Visual Studio에서 WCF 테스트 클라이언트를 시작 하는 경우 Visual Studio 디버깅 프로세스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="96257-226">Both of these actions also shut down WCF Service Auto Host and stop the Visual Studio debugging process if WCF Test Client was launched by Visual Studio.</span></span>

- <span data-ttu-id="96257-227">알림 영역에서 **WCF 서비스 호스트** 아이콘을 마우스 오른쪽 단추로 클릭 한 다음 끝내기를 클릭 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="96257-227">Right-click the **WCF Service Host** icon in the notification area, and then click **Exit.**</span></span> <span data-ttu-id="96257-228">그러면 WCF 서비스 자동 호스트와 WCF 테스트 클라이언트가 모두 종료 되 고 Visual Studio 디버깅 프로세스가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96257-228">This shuts down both WCF Service Auto Host and WCF Test Client and stops the Visual Studio debugging process.</span></span>

## <a name="see-also"></a><span data-ttu-id="96257-229">참조</span><span class="sxs-lookup"><span data-stu-id="96257-229">See also</span></span>

- [<span data-ttu-id="96257-230">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="96257-230">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
