---
title: ‘이 애플리케이션을 시작할 수 없음’ 문제 해결
description: "'이 애플리케이션을 시작할 수 없음' 대화 상자가 표시되면 어떻게 해야 하는지 알아보세요."
ms.date: 09/05/2019
ms.openlocfilehash: 92055bf40500eba4f7c892d11af12d8e675ddd5d
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605245"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a><span data-ttu-id="5613a-103">‘이 애플리케이션을 시작할 수 없음’ 오류 메시지 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5613a-103">Troubleshooting a 'This application could not be started' error message</span></span>

<span data-ttu-id="5613a-104">.NET Framework용으로 개발된 애플리케이션에서는 일반적으로 특정 버전의 .NET Framework를 시스템에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-104">Applications that are developed for .NET Framework typically require that a specific version of .NET Framework be installed on your system.</span></span> <span data-ttu-id="5613a-105">경우에 따라 설치된 버전이나 필요한 .NET Framework 버전 없이 애플리케이션을 실행하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-105">In some cases, you may attempt to run an application without either an installed version or the expected version of .NET Framework present.</span></span> <span data-ttu-id="5613a-106">이 경우 다음과 같은 오류 대화 상자가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-106">This often produces an error dialog box like the following:</span></span>

![이 애플리케이션을 시작할 수 없습니다.](media/application-not-started/app-could-not-be-started.png)

<span data-ttu-id="5613a-108">이 오류는 일반적으로 다음 조건 중 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-108">This error typically indicates one of the following conditions:</span></span>

- <span data-ttu-id="5613a-109">시스템의 .NET Framework 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-109">A .NET Framework installation on your system has become corrupted.</span></span>

- <span data-ttu-id="5613a-110">애플리케이션에 필요한 .NET Framework 버전을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-110">The version of .NET Framework needed by your application cannot be detected.</span></span>

<span data-ttu-id="5613a-111">애플리케이션을 실행할 수 있도록 이 문제를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-111">To address this issue so that you can run your application, do the following:</span></span>

1. <span data-ttu-id="5613a-112">[.NET Framework 복구 도구(NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135)를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-112">Download the [.NET Framework Repair Tool (NetFxRepairTool.exe)](https://www.microsoft.com/download/details.aspx?id=30135).</span></span> <span data-ttu-id="5613a-113">다운로드가 완료되면 도구가 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-113">The tool runs automatically when the download completes.</span></span>

1. <span data-ttu-id="5613a-114">.NET Framework 복구 도구에서 다음 그림에 표시된 것과 같은 추가 작업을 권장하는 경우 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-114">If the .NET Framework Repair Tool recommends any additional action, such as those shown in the following figure, select **Next**.</span></span>

   ![복구 도구 권장 변경 내용](media/application-not-started/repair-tool-recommended-changes.png)

1. <span data-ttu-id="5613a-116">.NET Framework 복구 도구는 다음 그림에 표시된 대화 상자를 표시하여 변경이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-116">The .NET Framework Repair Tools displays a dialog box shown in the following figure to indicate that changes are complete.</span></span> <span data-ttu-id="5613a-117">애플리케이션을 다시 실행하는 동안 이 대화 상자를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-117">Leave the dialog box open while you to try rerun your application.</span></span> <span data-ttu-id="5613a-118">.NET Framework 복구 도구에서 손상된 .NET Framework 설치를 확인하고 해결한 경우 이 작업은 성공입니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-118">This should succeed if the .NET Framework Repair Tool has identified and corrected a corrupted .NET Framework installation.</span></span>

   ![복구 도구 변경 완료](media/application-not-started/repair-tool-changes-complete.png)

1. <span data-ttu-id="5613a-120">애플리케이션이 성공적으로 실행되는 경우 **마침** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-120">If your application runs successfully, select the **Finish** button.</span></span> <span data-ttu-id="5613a-121">그렇지 않으면 **다음** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-121">Otherwise, select the **Next** button.</span></span>

1. <span data-ttu-id="5613a-122">**다음** 단추를 선택한 경우 .NET Framework 복구 도구는 다음과 같은 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-122">If you selected the **Next** button, the .NET Framework Repair Tool displays a dialog box like the following.</span></span> <span data-ttu-id="5613a-123">**마침** 단추를 선택하여 진단 정보를 Microsoft에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-123">Select the **Finish** button to send diagnostic information to Microsoft.</span></span>

   ![이 문제를 해결할 수 없음](media/application-not-started/repair-tool-no-resolution.png)

1. <span data-ttu-id="5613a-125">애플리케이션을 여전히 실행할 수 없는 경우 다음 표에 표시된 대로 사용 중인 Windows에서 지원하는 최신 버전의 .NET Framework를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-125">If you still cannot run the application, install the latest version of .NET Framework that's supported by your version of Windows, as shown in the following table.</span></span>

   |<span data-ttu-id="5613a-126">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="5613a-126">Windows version</span></span>|<span data-ttu-id="5613a-127">.NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="5613a-127">.NET Framework installation</span></span>|
   |---|---|
   |<span data-ttu-id="5613a-128">Windows 10 1주년 업데이트 이상 버전</span><span class="sxs-lookup"><span data-stu-id="5613a-128">Windows 10 Anniversary Update and later versions</span></span>|[<span data-ttu-id="5613a-129">.NET Framework 4.8 런타임</span><span class="sxs-lookup"><span data-stu-id="5613a-129">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="5613a-130">Windows 10, Windows 10 11월 업데이트</span><span class="sxs-lookup"><span data-stu-id="5613a-130">Windows 10, Windows 10 November Update</span></span>|[<span data-ttu-id="5613a-131">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="5613a-131">.NET Framework 4.6.2</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net462)|
   |<span data-ttu-id="5613a-132">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5613a-132">Windows 8.1</span></span>|[<span data-ttu-id="5613a-133">.NET Framework 4.8 런타임</span><span class="sxs-lookup"><span data-stu-id="5613a-133">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="5613a-134">Windows 8</span><span class="sxs-lookup"><span data-stu-id="5613a-134">Windows 8</span></span>|[<span data-ttu-id="5613a-135">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="5613a-135">.NET Framework 4.6.1</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net461)|
   |<span data-ttu-id="5613a-136">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="5613a-136">Windows 7 SP1</span></span>|[<span data-ttu-id="5613a-137">.NET Framework 4.8 런타임</span><span class="sxs-lookup"><span data-stu-id="5613a-137">.NET Framework 4.8 Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |<span data-ttu-id="5613a-138">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="5613a-138">Windows Vista SP2</span></span>|[<span data-ttu-id="5613a-139">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="5613a-139">.NET Framework 4.6</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net46)|

   > [!NOTE]
   > <span data-ttu-id="5613a-140">Windows 10 2019년 5월 업데이트에는 .NET Framework 4.8이 미리 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-140">.NET Framework 4.8 is preinstalled on Windows 10 May 2019 Update.</span></span>

1. <span data-ttu-id="5613a-141">애플리케이션을 시작하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-141">Attempt to launch the application.</span></span>

1. <span data-ttu-id="5613a-142">경우에 따라 .NET Framework 3.5를 설치하도록 요구하는 다음과 같은 대화 상자가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-142">In some cases, you may see a dialog box like the following, which asks you to install .NET Framework 3.5.</span></span> <span data-ttu-id="5613a-143">**이 기능 다운로드 및 설치** 를 선택하여 .NET Framework 3.5를 설치한 다음, 애플리케이션을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5613a-143">Select **Download and install this feature** to install .NET Framework 3.5, then launch the application again.</span></span>

   ![.NET Framework 3.5를 설치하도록 제안하는 Windows 기능 대화 상자](media/application-not-started/install-3-5.png)

## <a name="see-also"></a><span data-ttu-id="5613a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5613a-145">See also</span></span>

- [<span data-ttu-id="5613a-146">.NET Framework 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5613a-146">.NET Framework System Requirements</span></span>](../get-started/system-requirements.md)
- [<span data-ttu-id="5613a-147">.NET Framework 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="5613a-147">.NET Framework installation guide</span></span>](index.md)
- [<span data-ttu-id="5613a-148">차단된 .NET Framework 설치 및 제거 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5613a-148">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
