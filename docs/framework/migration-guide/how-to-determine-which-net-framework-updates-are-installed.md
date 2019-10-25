---
title: '방법: 설치된 .NET Framework 보안 업데이트 및 핫픽스 확인'
description: 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 알아봅니다.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c69d4bb370087dddafbfed41cbfb1fef229677c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318966"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="dbec2-103">방법: 설치된 .NET Framework 보안 업데이트 및 핫픽스 확인</span><span class="sxs-lookup"><span data-stu-id="dbec2-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="dbec2-104">이 문서에서는 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="dbec2-105">이 문서에 표시된 모든 방법을 사용하려면 관리자 권한이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="dbec2-106">레지스트리를 사용하여 설치된 업데이트를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="dbec2-106">To find installed updates using the registry</span></span>

<span data-ttu-id="dbec2-107">컴퓨터에 설치된 각 .NET Framework 버전에 대해 설치된 보안 업데이트 및 핫픽스는 Windows 레지스트리에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="dbec2-108">레지스트리 편집기(*regedit.exe*)를 사용하여 이 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="dbec2-109">**regedit.exe** 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="dbec2-110">Windows 8 및 이후 버전에서는 **시작** ![Windows 키 로고 스크린샷](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo")을 마우스 오른쪽 단추로 클릭한 다음 **실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="dbec2-111">**열기** 상자에 **regedit**를 입력하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="dbec2-112">레지스트리 편집기에서 다음 하위 키를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="dbec2-113">설치된 업데이트가 적용되는 .NET Framework 버전을 식별하는 하위 키 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="dbec2-114">각 업데이트는 KB(기술 자료) 번호로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="dbec2-115">레지스트리 편집기에서 .NET Framework 버전과 각 버전에 대해 설치된 업데이트는 서로 다른 하위 키에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="dbec2-116">설치된 버전 번호를 검색하는 방법에 대한 내용은 [방법: 설치된 .NET Framework 버전 확인](how-to-determine-which-versions-are-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbec2-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="dbec2-117">코드에서 레지스트리를 쿼리하여 설치된 업데이트를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="dbec2-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="dbec2-118">다음 예제에서는 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 프로그래밍 방식으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="dbec2-119">이 예제는 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="dbec2-120">PowerShell에서 레지스트리를 쿼리하여 설치된 업데이트를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="dbec2-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="dbec2-121">다음 예제에서는 PowerShell을 사용하여 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="dbec2-122">이 예제는 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbec2-122">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
Microsoft .NET Framework 4 Extended
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
```

## <a name="see-also"></a><span data-ttu-id="dbec2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbec2-123">See also</span></span>

- [<span data-ttu-id="dbec2-124">방법: 설치된 .NET Framework 버전 확인</span><span class="sxs-lookup"><span data-stu-id="dbec2-124">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="dbec2-125">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="dbec2-125">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="dbec2-126">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="dbec2-126">Versions and dependencies</span></span>](versions-and-dependencies.md)
