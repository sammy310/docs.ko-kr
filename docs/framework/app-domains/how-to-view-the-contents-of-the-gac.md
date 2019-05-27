---
title: '방법: 글로벌 어셈블리 캐시의 내용 보기'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c7d197ea7178abf991247e5ecca02c2b8e94713
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634366"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="1e3a8-102">방법: 글로벌 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="1e3a8-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="1e3a8-103">[전역 어셈블리 캐시 도구(Gacutil.exe)](../tools/gacutil-exe-gac-tool.md)를 사용하면 GAC(전역 어셈블리 캐시)의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="1e3a8-104">GAC의 어셈블리 보기</span><span class="sxs-lookup"><span data-stu-id="1e3a8-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="1e3a8-105">전역 어셈블리 캐시의 어셈블리 목록을 보려면 [Visual Studio에 대한 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 열고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="1e3a8-106">또는</span><span class="sxs-lookup"><span data-stu-id="1e3a8-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="1e3a8-107">이전 버전의 .NET Framework에서는 [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="1e3a8-108">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 Shfusion.dll이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-108">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e3a8-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e3a8-109">See also</span></span>

- [<span data-ttu-id="1e3a8-110">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="1e3a8-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="1e3a8-111">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
