---
ms.openlocfilehash: 814372535f5c7a91f1df250404018228e4c4c812
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73198514"
---

> [!NOTE]
> <span data-ttu-id="85ae8-101">이 문서의 일부 C# 예제는 [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) 인라인 코드 실행기 및 플레이그라운드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-101">Some of the C# examples in this article run in the [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) inline code runner and playground.</span></span> <span data-ttu-id="85ae8-102">대화형 창에서 예제를 실행하려면 **실행** 버튼을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-102">Select the **Run** button to run an example in an interactive window.</span></span> <span data-ttu-id="85ae8-103">코드를 실행하면 **실행**을 다시 선택하여 코드를 수정하고 수정된 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-103">Once you execute the code, you can modify it and run the modified code by selecting **Run** again.</span></span> <span data-ttu-id="85ae8-104">수정된 코드는 대화형 창에서 실행되거나, 컴파일이 실패하면 대화형 창에 모든 C# 컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-104">The modified code either runs in the interactive window or, if compilation fails, the interactive window displays all C# compiler error messages.</span></span>
>
> <span data-ttu-id="85ae8-105">[Try.NET](xref:System.TimeZoneInfo.Local) 인라인 코드 러너와 플레이그라운드의 [현지 표준 시간대](https://dotnet.microsoft.com/platform/try-dotnet)는 협정 세계시(또는 UTC)입니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-105">The [local time zone](xref:System.TimeZoneInfo.Local) of the [Try.NET](https://dotnet.microsoft.com/platform/try-dotnet) inline code runner and playground is Coordinated Universal Time, or UTC.</span></span> <span data-ttu-id="85ae8-106">이는 <xref:System.DateTime>, <xref:System.DateTimeOffset> 및 <xref:System.TimeZoneInfo> 형식과 이러한 형식의 멤버를 보여주는 예제의 동작 및 출력에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ae8-106">This may affect the behavior and the output of examples that illustrate the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types and their members.</span></span>
