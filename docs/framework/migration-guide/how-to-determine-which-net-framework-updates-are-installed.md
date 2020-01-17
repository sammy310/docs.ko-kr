---
title: 설치된 .NET Framework 보안 업데이트 및 핫픽스 참조
description: 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 알아봅니다.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 087519048b412798ef7495d250dc2538ee5c2fd0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716264"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="9618b-103">설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="9618b-103">How to determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="9618b-104">이 문서에서는 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="9618b-105">이 문서에 표시된 모든 방법을 사용하려면 관리자 권한이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="use-registry-editor"></a><span data-ttu-id="9618b-106">레지스트리 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="9618b-106">Use Registry Editor</span></span>

<span data-ttu-id="9618b-107">컴퓨터에 설치된 각 .NET Framework 버전에 대해 설치된 보안 업데이트 및 핫픽스는 Windows 레지스트리에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="9618b-108">레지스트리 편집기(*regedit.exe*)를 사용하여 이 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="9618b-109">**regedit.exe** 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="9618b-110">Windows 8 및 이후 버전에서는 **시작** ![Windows 키 로고 스크린샷](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo")을 마우스 오른쪽 단추로 클릭한 다음 **실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="9618b-111">**열기** 상자에 **regedit**를 입력하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="9618b-112">레지스트리 편집기에서 다음 하위 키를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-112">In the Registry Editor, open the following subkey:</span></span>

     <span data-ttu-id="9618b-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span><span class="sxs-lookup"><span data-stu-id="9618b-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span></span>

     <span data-ttu-id="9618b-114">설치된 업데이트가 적용되는 .NET Framework 버전을 식별하는 하위 키 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-114">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="9618b-115">각 업데이트는 KB(기술 자료) 번호로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-115">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="9618b-116">레지스트리 편집기에서 .NET Framework 버전과 각 버전에 대해 설치된 업데이트는 서로 다른 하위 키에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-116">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="9618b-117">설치된 버전 번호를 검색하는 방법에 대한 내용은 [방법: 설치된 .NET Framework 버전 확인](how-to-determine-which-versions-are-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9618b-117">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="query-the-registry-using-code"></a><span data-ttu-id="9618b-118">코드를 사용하여 레지스트리를 쿼리</span><span class="sxs-lookup"><span data-stu-id="9618b-118">Query the registry using code</span></span>

<span data-ttu-id="9618b-119">다음 예제에서는 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 프로그래밍 방식으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-119">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="9618b-120">이 예제는 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-120">The example produces an output that's similar to the following one:</span></span>

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

## <a name="use-powershell-to-query-the-registry"></a><span data-ttu-id="9618b-121">PowerShell을 사용하여 레지스트리를 쿼리</span><span class="sxs-lookup"><span data-stu-id="9618b-121">Use PowerShell to query the registry</span></span>

<span data-ttu-id="9618b-122">다음 예제에서는 PowerShell을 사용하여 컴퓨터에 설치된 .NET Framework 보안 업데이트 및 핫픽스를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-122">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="9618b-123">이 예제는 다음과 유사한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9618b-123">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9618b-124">참조</span><span class="sxs-lookup"><span data-stu-id="9618b-124">See also</span></span>

- [<span data-ttu-id="9618b-125">방법: 설치된 .NET Framework 버전 확인</span><span class="sxs-lookup"><span data-stu-id="9618b-125">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="9618b-126">개발자용 .NET Framework 설치</span><span class="sxs-lookup"><span data-stu-id="9618b-126">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="9618b-127">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="9618b-127">Versions and dependencies</span></span>](versions-and-dependencies.md)
