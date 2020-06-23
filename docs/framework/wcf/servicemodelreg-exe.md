---
title: ServiceModel 등록 도구(ServiceModelReg.exe)
description: 서비스 활성화에 문제가 발생 하는 경우이 명령줄 도구를 사용 하 여 단일 컴퓨터에서 WCF 및 WF 구성 요소를 등록 하는 작업을 관리할 수 있습니다.
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: 347b1b8071abe7d8eb7e16ffd879c1fdb9825bc7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245897"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a><span data-ttu-id="cf8b0-103">ServiceModel 등록 도구(ServiceModelReg.exe)</span><span class="sxs-lookup"><span data-stu-id="cf8b0-103">ServiceModel Registration Tool (ServiceModelReg.exe)</span></span>
<span data-ttu-id="cf8b0-104">이 명령줄 도구는 단일 컴퓨터에서 WCF 및 WF 구성 요소 등록을 관리하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-104">This command-line tool provides the ability to manage the registration of WCF and WF components on a single machine.</span></span> <span data-ttu-id="cf8b0-105">일반적인 경우에는 설치 시 WCF 및 WF 구성 요소가 구성되므로 이 도구를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-105">Under normal circumstances you should not need to use this tool as WCF and WF components are configured when installed.</span></span> <span data-ttu-id="cf8b0-106">하지만 서비스 활성화 문제가 있는 경우 이 도구를 사용하여 구성 요소를 등록해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-106">But if you are experiencing problems with service activation, you can try to register the components using this tool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8b0-107">구문</span><span class="sxs-lookup"><span data-stu-id="cf8b0-107">Syntax</span></span>  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf8b0-108">설명</span><span class="sxs-lookup"><span data-stu-id="cf8b0-108">Remarks</span></span>  
 <span data-ttu-id="cf8b0-109">이 도구는 다음 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-109">The tool can be found in the following location:</span></span>  
  
 <span data-ttu-id="cf8b0-110">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cf8b0-110">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
> [!NOTE]
> <span data-ttu-id="cf8b0-111">ServiceModel 등록 도구가 Windows Vista에서 실행 되는 경우 **Windows 기능** 대화 상자에 **Microsoft .NET Framework 3.0** 의 **Windows Communication Foundation HTTP 활성화** 옵션이 설정 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-111">When the ServiceModel Registration Tool is run on Windows Vista, the **Windows Features** dialog may not reflect that the **Windows Communication Foundation HTTP Activation** option under **Microsoft .NET Framework 3.0** is turned on.</span></span> <span data-ttu-id="cf8b0-112">**시작**을 클릭 하 고 **실행** 을 클릭 한 다음 **OptionalFeatures**를 입력 하 여 **Windows 기능** 대화 상자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-112">The **Windows Features** dialog can be accessed by clicking **Start**, then click **Run** and then typing **OptionalFeatures**.</span></span>  
  
 <span data-ttu-id="cf8b0-113">다음 표에서는 ServiceModelReg.exe와 함께 사용할 수 있는 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-113">The following tables describe the options that can be used with ServiceModelReg.exe.</span></span>  
  
|<span data-ttu-id="cf8b0-114">옵션</span><span class="sxs-lookup"><span data-stu-id="cf8b0-114">Option</span></span>|<span data-ttu-id="cf8b0-115">Description</span><span class="sxs-lookup"><span data-stu-id="cf8b0-115">Description</span></span>|  
|------------|-----------------|  
|`-ia`|<span data-ttu-id="cf8b0-116">모든 WCF 및 WF 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-116">Installs all WCF and WF components.</span></span>|  
|`-ua`|<span data-ttu-id="cf8b0-117">모든 WCF 및 WF 구성 요소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-117">Uninstalls all WCF and WF components.</span></span>|  
|`-r`|<span data-ttu-id="cf8b0-118">모든 WCF 및 WF 구성 요소를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-118">Repairs all WCF and WF components.</span></span>|  
|`-i`|<span data-ttu-id="cf8b0-119">-c로 지정된 WCF 및 WF 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-119">Installs WCF and WF components specified with –c.</span></span>|  
|`-u`|<span data-ttu-id="cf8b0-120">-c로 지정된 WCF 및 WF 구성 요소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-120">Uninstalls WCF and WF components specified with –c.</span></span>|  
|`-c`|<span data-ttu-id="cf8b0-121">구성 요소를 설치 또는 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-121">Installs or uninstalls a component:</span></span><br /><br /> <span data-ttu-id="cf8b0-122">-httpnamespace – HTTP 네임 스페이스 예약</span><span class="sxs-lookup"><span data-stu-id="cf8b0-122">-   httpnamespace – HTTP Namespace Reservation</span></span><br /><span data-ttu-id="cf8b0-123">-tcpportsharing – TCP 포트 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="cf8b0-123">-   tcpportsharing – TCP port sharing service</span></span><br /><span data-ttu-id="cf8b0-124">-tcpactivation – TCP 활성화 서비스 (.NET 4 클라이언트 프로필에 지원 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="cf8b0-124">-   tcpactivation – TCP activation service (unsupported on .NET 4 Client Profile)</span></span><br /><span data-ttu-id="cf8b0-125">-namedpipeactivation – 명명 된 파이프 활성화 서비스 (.NET 4 클라이언트 프로필에 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="cf8b0-125">-   namedpipeactivation – Named pipe activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="cf8b0-126">-msmqactivation 서비스가 – MSMQ 활성화 서비스 (.NET 4 클라이언트 프로필에 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="cf8b0-126">-   msmqactivation – MSMQ activation service (unsupported on .NET 4 Client Profile</span></span><br /><span data-ttu-id="cf8b0-127">-etw – ETW 이벤트 추적 매니페스트 (Windows Vista 이상)</span><span class="sxs-lookup"><span data-stu-id="cf8b0-127">-   etw – ETW event tracing manifests (Windows Vista or later)</span></span>|  
|`-q`|<span data-ttu-id="cf8b0-128">자동 모드(오류 기록만 표시함)</span><span class="sxs-lookup"><span data-stu-id="cf8b0-128">Quiet mode (only display error logging)</span></span>|  
|`-v`|<span data-ttu-id="cf8b0-129">자세한 정보 표시 모드.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-129">Verbose mode.</span></span>|  
|`-nologo`|<span data-ttu-id="cf8b0-130">저작권 및 배너 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-130">Suppresses the copyright and banner message.</span></span>|  
|`-?`|<span data-ttu-id="cf8b0-131">도움말 텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="cf8b0-131">Displays help text</span></span>|  
  
## <a name="fixing-the-fileloadexception-error"></a><span data-ttu-id="cf8b0-132">FileLoadException 오류 수정</span><span class="sxs-lookup"><span data-stu-id="cf8b0-132">Fixing the FileLoadException Error</span></span>  
 <span data-ttu-id="cf8b0-133">컴퓨터에 이전 버전의 WCF를 설치한 경우 `FileLoadFoundException` servicemodelreg.exe 도구를 실행 하 여 새 설치를 등록할 때 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-133">If you installed previous versions of WCF on your machine, you may get a `FileLoadFoundException` error when you run the ServiceModelReg tool to register a new installation.</span></span> <span data-ttu-id="cf8b0-134">이전 설치에서 파일을 수동으로 제거했지만 machine.config 설정이 그대로 남아 있으면 이 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-134">This can happen even if you have manually removed files from the previous install, but left the machine.config settings intact.</span></span>  
  
 <span data-ttu-id="cf8b0-135">다음과 유사한 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-135">The error message is similar to the following.</span></span>  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 <span data-ttu-id="cf8b0-136">오류 메시지에 따르면 System.ServiceModel 버전 2.0.0.0 어셈블리가 초기 CTP(Customer Technology Preview) 릴리스에 의해 설치되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-136">You should note from the error message that the System.ServiceModel Version 2.0.0.0 assembly was installed by an early Customer Technology Preview (CTP) release.</span></span> <span data-ttu-id="cf8b0-137">릴리스된 System.ServiceModel 어셈블리의 현재 버전은 3.0.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-137">The current version of the System.ServiceModel assembly released is 3.0.0.0 instead.</span></span> <span data-ttu-id="cf8b0-138">따라서이 문제는 WCF의 초기 CTP 릴리스가 설치 되었지만 완전히 제거 되지 않은 컴퓨터에 공식 WCF 릴리스를 설치 하려는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-138">Therefore, this issue is encountered when you want to install the official WCF release on a machine where an early CTP release of WCF was installed, but not completely uninstalled.</span></span>  
  
 <span data-ttu-id="cf8b0-139">ServiceModelReg.exe는 이전 버전의 항목을 정리할 수 없으며 새 버전의 항목을 등록할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-139">ServiceModelReg.exe cannot clean up prior version entries, nor can it register the new version's entries.</span></span> <span data-ttu-id="cf8b0-140">유일한 해결 방법은 machine.config를 수동으로 편집 하는 것입니다. 이 파일은 다음 위치에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-140">The only workaround is to manually edit machine.config. You can locate this file at the following location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="cf8b0-141">64 비트 컴퓨터에서 WCF를 실행 하는 경우에도이 위치에서 동일한 파일을 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-141">If you are running WCF on a 64-bit machine, you should also edit the same file at this location.</span></span>  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 <span data-ttu-id="cf8b0-142">이 파일에서 "System.servicemodel, Version = 2.0.0.0"을 참조 하는 XML 노드를 찾아 삭제 하 고 자식 노드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-142">Locate any XML nodes in this file that refer to "System.ServiceModel, Version=2.0.0.0", delete them and any child nodes.</span></span> <span data-ttu-id="cf8b0-143">파일을 저장하고 ServiceModelReg.exe를 다시 실행하면 이 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-143">Save the file and re-run ServiceModelReg.exe resolves this problem.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cf8b0-144">예제</span><span class="sxs-lookup"><span data-stu-id="cf8b0-144">Examples</span></span>  
 <span data-ttu-id="cf8b0-145">다음 예제에서는 ServiceModelReg.exe 도구의 가장 일반적인 옵션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf8b0-145">The following examples show how to use the most common options of the ServiceModelReg.exe tool.</span></span>  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
