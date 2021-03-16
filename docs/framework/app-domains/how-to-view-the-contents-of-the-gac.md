---
title: '방법: 글로벌 어셈블리 캐시의 내용 보기'
description: GAC(전역 어셈블리 캐시) 도구(gacutil.exe)를 사용하여 .NET에서 전역 어셈블리 캐시의 콘텐츠를 보는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: a40c371e6f95f6c90ecbfbf28183226632a58e5b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258314"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="fe5bf-103">방법: 글로벌 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="fe5bf-103">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="fe5bf-104">[전역 어셈블리 캐시 도구(Gacutil.exe)](../tools/gacutil-exe-gac-tool.md)를 사용하면 GAC(전역 어셈블리 캐시)의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5bf-104">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="fe5bf-105">GAC의 어셈블리 보기</span><span class="sxs-lookup"><span data-stu-id="fe5bf-105">View the assemblies in the GAC</span></span>

<span data-ttu-id="fe5bf-106">전역 어셈블리 캐시의 어셈블리 목록을 보려면 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 열고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe5bf-106">To view a list of the assemblies in the global assembly cache, open a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="fe5bf-107">또는</span><span class="sxs-lookup"><span data-stu-id="fe5bf-107">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="fe5bf-108">이전 버전의 .NET Framework에서는 [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5bf-108">In earlier versions of .NET Framework, the [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="fe5bf-109">.NET Framework 4부터는 Shfusion.dll이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe5bf-109">Beginning with .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe5bf-110">참조</span><span class="sxs-lookup"><span data-stu-id="fe5bf-110">See also</span></span>

- [<span data-ttu-id="fe5bf-111">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="fe5bf-111">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="fe5bf-112">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="fe5bf-112">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
