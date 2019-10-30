---
title: '방법: 전역 어셈블리 캐시의 내용 보기'
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
ms.openlocfilehash: b5d8b31e7eb23789878da620f3a4517056a1ee3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119826"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="b7eda-102">방법: 전역 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="b7eda-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="b7eda-103">[전역 어셈블리 캐시 도구(Gacutil.exe)](../tools/gacutil-exe-gac-tool.md)를 사용하면 GAC(전역 어셈블리 캐시)의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7eda-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="b7eda-104">GAC의 어셈블리 보기</span><span class="sxs-lookup"><span data-stu-id="b7eda-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="b7eda-105">전역 어셈블리 캐시의 어셈블리 목록을 보려면 [Visual Studio에 대한 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 열고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7eda-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="b7eda-106">또는</span><span class="sxs-lookup"><span data-stu-id="b7eda-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="b7eda-107">이전 버전의 .NET Framework에서는 [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7eda-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="b7eda-108">.NET Framework 4부터는 Shfusion.dll이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7eda-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7eda-109">참조</span><span class="sxs-lookup"><span data-stu-id="b7eda-109">See also</span></span>

- [<span data-ttu-id="b7eda-110">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="b7eda-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="b7eda-111">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="b7eda-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
