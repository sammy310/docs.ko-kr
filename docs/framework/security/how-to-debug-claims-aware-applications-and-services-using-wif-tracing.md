---
title: '방법: WIF 추적을 사용하여 클레임 인식 애플리케이션 및 서비스 디버그'
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: effd670a4d0e12f0bca10301fabc361c73e03328
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625874"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="ea663-102">방법: WIF 추적을 사용하여 클레임 인식 애플리케이션 및 서비스 디버그</span><span class="sxs-lookup"><span data-stu-id="ea663-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="ea663-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="ea663-103">Applies To</span></span>  
  
- <span data-ttu-id="ea663-104">Microsoft® Windows® Identity Foundation(WIF)</span><span class="sxs-lookup"><span data-stu-id="ea663-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="ea663-105">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="ea663-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
- <span data-ttu-id="ea663-106">문제 해결 및 WIF 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="ea663-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ea663-107">요약</span><span class="sxs-lookup"><span data-stu-id="ea663-107">Summary</span></span>  
 <span data-ttu-id="ea663-108">이 방법에서는 WIF 추적을 구성하고 추적 로그를 수집하는 방법 및 추적 뷰어 도구를 사용하여 추적 로그를 분석하는 방법의 필수 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="ea663-109">WIF와 관련된 문제를 해결하는 데 필요한 작업에 추적 항목을 매핑하는 일반적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="ea663-110">목차</span><span class="sxs-lookup"><span data-stu-id="ea663-110">Contents</span></span>  
  
- <span data-ttu-id="ea663-111">목표</span><span class="sxs-lookup"><span data-stu-id="ea663-111">Objectives</span></span>  
  
- <span data-ttu-id="ea663-112">단계 요약</span><span class="sxs-lookup"><span data-stu-id="ea663-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="ea663-113">1단계 - Web.config 구성 파일을 사용하여 WIF 추적 구성</span><span class="sxs-lookup"><span data-stu-id="ea663-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="ea663-114">2단계 - 추적 뷰어 도구를 사용하여 WIF 추적 파일 분석</span><span class="sxs-lookup"><span data-stu-id="ea663-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="ea663-115">3단계 - WIF 관련 문제를 해결할 수 있는 솔루션 식별</span><span class="sxs-lookup"><span data-stu-id="ea663-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
- <span data-ttu-id="ea663-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ea663-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="ea663-117">목표</span><span class="sxs-lookup"><span data-stu-id="ea663-117">Objectives</span></span>  
  
- <span data-ttu-id="ea663-118">WIF 추적을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-118">Configure WIF tracing.</span></span>  
  
- <span data-ttu-id="ea663-119">추적 뷰어 도구에서 추적 로그를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-119">View trace logs in the Trace Viewer tool.</span></span>  
  
- <span data-ttu-id="ea663-120">추적 로그에서 WIF 관련 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-120">Identify WIF related issues in the trace logs.</span></span>  
  
- <span data-ttu-id="ea663-121">추적 로그에서 발견된 WIF 관련 문제에 정정 작업을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="ea663-122">단계 요약</span><span class="sxs-lookup"><span data-stu-id="ea663-122">Summary of Steps</span></span>  
  
- <span data-ttu-id="ea663-123">1단계 - Web.config 구성 파일을 사용하여 WIF 추적 구성</span><span class="sxs-lookup"><span data-stu-id="ea663-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="ea663-124">2단계 - 추적 뷰어 도구를 사용하여 WIF 추적 파일 분석</span><span class="sxs-lookup"><span data-stu-id="ea663-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="ea663-125">3단계 - WIF 관련 문제를 해결할 수 있는 솔루션 식별</span><span class="sxs-lookup"><span data-stu-id="ea663-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="ea663-126">1단계 - Web.config 구성 파일을 사용하여 WIF 추적 구성</span><span class="sxs-lookup"><span data-stu-id="ea663-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="ea663-127">이 단계에서는 WIF가 해당 이벤트를 추적하고 추적 로그에 저장할 수 있도록 하는 변경 내용을 *Web.config* 파일의 구성 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="ea663-128">Web.config 구성 파일을 사용하여 WIF 추적을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="ea663-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1. <span data-ttu-id="ea663-129">Visual Studio 편집기의 **솔루션 탐색기**에서 루트 **Web.config** 또는 **App.config** 구성 파일을 두 번 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="ea663-130">솔루션에 **Web.config** 또는 **App.config** 구성 파일이 없는 경우 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목...** 을 차례로 클릭하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="ea663-131">**새 항목** 대화 상자의 목록에서 **App.config**에 대해 **응용 프로그램 구성 파일**을 선택하거나 **Web.config**에 대해 **웹 구성 파일**을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2. <span data-ttu-id="ea663-132">구성 파일의 끝에 있는 **\<configuration>** 노드 내에 다음과 비슷한 구성 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. <span data-ttu-id="ea663-133">위의 구성은 WIF에 자세한 추적 이벤트를 생성하고 *WIFTrace.e2e* 파일에 기록하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="ea663-134">에 대 한 값의 전체 목록은 합니다 **switchValue** 전환 다음 항목에에서 나와 있는 추적 수준 표를 참조 하세요. [추적 구성](../wcf/diagnostics/tracing/configuring-tracing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="ea663-135">2단계 - 추적 뷰어 도구를 사용하여 WIF 추적 파일 분석</span><span class="sxs-lookup"><span data-stu-id="ea663-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="ea663-136">이 단계에서는 추적 뷰어 도구(SvcTraceViewer.exe)를 사용하여 WIF 추적 로그를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="ea663-137">추적 뷰어 도구(SvcTraceViewer.exe)를 사용하여 WIF 추적 로그를 분석하려면</span><span class="sxs-lookup"><span data-stu-id="ea663-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1. <span data-ttu-id="ea663-138">추적 뷰어 도구(SvcTraceViewer.exe)는 Windows SDK의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="ea663-139">Windows SDK를 아직 설치 하지 않은 경우 여기서 다운로드할 수 있습니다. [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="ea663-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2. <span data-ttu-id="ea663-140">추적 뷰어 도구(SvcTraceViewer.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="ea663-141">일반적으로 설치 경로의 **Bin** 폴더에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3. <span data-ttu-id="ea663-142">메뉴에서 **파일**, **열기...**</span><span class="sxs-lookup"><span data-stu-id="ea663-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="ea663-143">옵션을 선택하거나 **Ctrl+O** 바로 가기를 사용하여 WIF 추적 로그 파일(예: WIFTrace.e2e)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="ea663-144">추적 로그 파일이 추적 뷰어 도구에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4. <span data-ttu-id="ea663-145">**작업** 탭에서 항목을 검토합니다. 각 항목에는 작업 수, 기록된 추적 수, 작업 기간, 시작 및 종료 타임스탬프가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5. <span data-ttu-id="ea663-146">**작업** 탭을 클릭합니다. 자세한 추적 항목이 도구의 주 영역에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="ea663-147">사용 된 **수준** 예를 들어 특정 수준의 추적을 필터링 하려면 메뉴의 드롭다운 목록: **모든**, **경고**, **오류**하십시오 **정보**등.</span><span class="sxs-lookup"><span data-stu-id="ea663-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6. <span data-ttu-id="ea663-148">특정 추적 항목을 클릭하여 도구의 아래쪽 영역에서 세부 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="ea663-149">해당 탭을 선택하여 **서식 있음** 및 **XML** 뷰에서 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="ea663-150">3단계 - WIF 관련 문제를 해결할 수 있는 솔루션 식별</span><span class="sxs-lookup"><span data-stu-id="ea663-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="ea663-151">이 단계에서는 WIF 추적 로그 및 추적 뷰어 도구를 사용하여 식별된 WIF 관련 문제에 대한 솔루션을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="ea663-152">문제 해결을 위해 WIF 관련 예외를 잠재적인 솔루션이나 필수 작업에 매핑하는 일반적인 매핑을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="ea663-153">WIF 관련 문제를 해결할 수 있는 솔루션을 식별하려면</span><span class="sxs-lookup"><span data-stu-id="ea663-153">To identify solutions to fix WIF related issues</span></span>  
  
1. <span data-ttu-id="ea663-154">WIF 예외 및 필수 작업이 포함된 다음 표를 검토하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="ea663-155">**오류 ID**</span><span class="sxs-lookup"><span data-stu-id="ea663-155">**Error ID**</span></span>|<span data-ttu-id="ea663-156">**오류 메시지**</span><span class="sxs-lookup"><span data-stu-id="ea663-156">**Error Message**</span></span>|<span data-ttu-id="ea663-157">**오류를 해결하는 데 필요한 작업**</span><span class="sxs-lookup"><span data-stu-id="ea663-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="ea663-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="ea663-158">ID4175</span></span>|<span data-ttu-id="ea663-159">보안 토큰의 발급자가 IssuerNameRegistry에서 인식되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="ea663-160">이 발급자의 보안 토큰을 수락하려면 이 발급자에 대한 유효한 이름을 반환하도록 IssuerNameRegistry를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="ea663-161">MMC 스냅인에서 지문을 복사하고 *Web.config* 파일에 붙여넣으면 이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="ea663-162">특히, 인증서 속성 창에서 복사하는 경우 텍스트 문자열에서 인쇄할 수 없는 추가 문자를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="ea663-163">이 추가 문자로 인해 지문 일치가 실패 합니다. 합니다. 지문을 올바르게 복사 하는 절차를 찾을 수 있습니다 [Single Sign 클레임 기반-에서 웹 및 Microsoft Azure에 대 한](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea663-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found at [Claims-Based Single Sign-On for the Web and Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="ea663-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ea663-164">Related Items</span></span>  
  
- [<span data-ttu-id="ea663-165">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ea663-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
