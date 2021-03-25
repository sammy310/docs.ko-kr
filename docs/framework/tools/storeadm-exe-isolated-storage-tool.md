---
title: Storeadm.exe(격리된 스토리지 도구)
description: 격리된 스토리지 도구인 Storeadm.exe에 대해 알아봅니다. 이 도구를 사용하여 현재 사용자의 기존 저장소를 모두 표시하거나 제거할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 1bd7aee54af8ec78454d9c9023856966beb91174
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653610"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="ef603-104">Storeadm.exe(격리된 스토리지 도구)</span><span class="sxs-lookup"><span data-stu-id="ef603-104">Storeadm.exe (Isolated Storage Tool)</span></span>

<span data-ttu-id="ef603-105">격리된 스토리지 도구를 사용하면 현재 사용자의 기존 저장소를 모두 표시하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-105">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="ef603-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="ef603-107">도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-107">To run the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>
  
 <span data-ttu-id="ef603-108">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-108">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef603-109">구문</span><span class="sxs-lookup"><span data-stu-id="ef603-109">Syntax</span></span>  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef603-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef603-110">Parameters</span></span>  
  
|<span data-ttu-id="ef603-111">옵션</span><span class="sxs-lookup"><span data-stu-id="ef603-111">Option</span></span>|<span data-ttu-id="ef603-112">설명</span><span class="sxs-lookup"><span data-stu-id="ef603-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ef603-113">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="ef603-113">**/h**[**elp**]</span></span>|<span data-ttu-id="ef603-114">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-114">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="ef603-115">**/list**</span><span class="sxs-lookup"><span data-stu-id="ef603-115">**/list**</span></span>|<span data-ttu-id="ef603-116">현재 사용자의 기존 저장소를 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-116">Displays all existing stores for the current user.</span></span> <span data-ttu-id="ef603-117">여기에는 해당 사용자가 실행한 모든 애플리케이션 또는 어셈블리의 저장소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-117">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="ef603-118">**/machine**</span><span class="sxs-lookup"><span data-stu-id="ef603-118">**/machine**</span></span>|<span data-ttu-id="ef603-119">컴퓨터 저장소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-119">Selects the machine store.</span></span> <span data-ttu-id="ef603-120">이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 컴퓨터 저장소에 적용되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-120">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="ef603-121">.NET Framework 2.0에 새로 추가된 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-121">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="ef603-122">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="ef603-122">**/quiet**</span></span>|<span data-ttu-id="ef603-123">자동 모드를 지정합니다. 오류 메시지만 표시되도록 자세한 정보는 출력하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-123">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="ef603-124">**/remove**</span><span class="sxs-lookup"><span data-stu-id="ef603-124">**/remove**</span></span>|<span data-ttu-id="ef603-125">현재 사용자의 기존 저장소를 모두 영구 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-125">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="ef603-126">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="ef603-126">**/roaming**</span></span>|<span data-ttu-id="ef603-127">로밍 저장소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-127">Selects the roaming store.</span></span> <span data-ttu-id="ef603-128">이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 로밍 저장소에 적용되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-128">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="ef603-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="ef603-129">**/?**</span></span>|<span data-ttu-id="ef603-130">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-130">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef603-131">설명</span><span class="sxs-lookup"><span data-stu-id="ef603-131">Remarks</span></span>  

 <span data-ttu-id="ef603-132">아무 옵션도 지정하지 않고 명령줄에서 Storeadm.exe를 실행하면 이 도구의 구문 및 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-132">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="ef603-133">**/list** 옵션 및 **/remove** 옵션은 일반적으로 한 번에 하나만 사용되지만 둘 이상의 옵션을 지정한 경우에는 명령줄에 표시된 순서대로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-133">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="ef603-134">애플리케이션에서는 두 개의 사용자용 저장소 중 하나 또는 컴퓨터 저장소를 선택하여 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-134">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
- <span data-ttu-id="ef603-135">로컬 저장소는 해당 사용자에 대해 사용자 데이터 로밍이 사용되는 경우에도 로밍되지 않는 위치에 있습니다(Windows 2000 이상의 경우).</span><span class="sxs-lookup"><span data-stu-id="ef603-135">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
- <span data-ttu-id="ef603-136">로밍 저장소는 로밍할 수 있는 위치에 있지만 Windows NT 관리를 통해 해당 사용자에 대해 로밍이 사용되는 경우에만 로밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-136">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
- <span data-ttu-id="ef603-137">컴퓨터 저장소는 컴퓨터의 모든 사용자에게 공통적이며 해당 컴퓨터의 공용 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-137">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef603-138">컴퓨터 저장소는 .NET Framework 버전 2.0에서 새로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-138">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="ef603-139">사용자에 대해 로밍이 실제로 사용되는지 여부는 Storeadm.exe의 관리에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-139">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="ef603-140">옵션 없이 이 도구를 실행하면 모든 작업이 로컬 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-140">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="ef603-141">**/roaming** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 로밍 가능한 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-141">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="ef603-142">**/machine** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 컴퓨터 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef603-142">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef603-143">참조</span><span class="sxs-lookup"><span data-stu-id="ef603-143">See also</span></span>

- [<span data-ttu-id="ef603-144">도구</span><span class="sxs-lookup"><span data-stu-id="ef603-144">Tools</span></span>](index.md)
- [<span data-ttu-id="ef603-145">격리된 스토리지</span><span class="sxs-lookup"><span data-stu-id="ef603-145">Isolated Storage</span></span>](../../standard/io/isolated-storage.md)
- [<span data-ttu-id="ef603-146">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="ef603-146">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
