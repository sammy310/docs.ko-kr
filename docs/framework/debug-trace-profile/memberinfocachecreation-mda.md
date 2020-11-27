---
title: memberInfoCacheCreation MDA
description: MemberInfo 캐시가 생성 될 때 활성화 되는 .NET의 memberInfoCacheCreation MDA (관리 디버깅 도우미)를 이해 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
ms.openlocfilehash: 44d279a949ca0b35c46f805e65eb6f61ffb532f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271163"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="32851-103">memberInfoCacheCreation MDA</span><span class="sxs-lookup"><span data-stu-id="32851-103">memberInfoCacheCreation MDA</span></span>

<span data-ttu-id="32851-104">`memberInfoCacheCreation` MDA(관리 디버깅 도우미)는 <xref:System.Reflection.MemberInfo> 캐시를 만들 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="32851-104">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="32851-105">리소스 사용량이 많은 리플렉션 기능을 활용하는 프로그램을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32851-105">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="32851-106">증상</span><span class="sxs-lookup"><span data-stu-id="32851-106">Symptoms</span></span>  

 <span data-ttu-id="32851-107">프로그램에서 리소스 사용량이 많은 리플렉션을 사용하므로 프로그램의 작업 집합이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="32851-107">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="32851-108">원인</span><span class="sxs-lookup"><span data-stu-id="32851-108">Cause</span></span>  

 <span data-ttu-id="32851-109"><xref:System.Reflection.MemberInfo> 개체와 관련된 리플렉션 작업은 콜드 페이지에 저장된 메타데이터를 읽고 일반적으로 프로그램에서 런타임에 바인딩된 시나리오 형식을 사용하는 것을 나타내므로 리소스 이용률이 높은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="32851-109">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="32851-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="32851-110">Resolution</span></span>  

 <span data-ttu-id="32851-111">이 MDA를 사용하도록 설정하고 디버거에서 코드를 실행하거나 MDA가 활성화될 때 디버거와 연결하여 프로그램에서 리플렉션이 사용되는 위치를 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-111">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="32851-112">디버거에서 <xref:System.Reflection.MemberInfo> 캐시가 생성된 위치를 보여 주는 스택 추적을 얻을 수 있으며, 여기에서 프로그램이 리플렉션을 사용하는 위치를 판별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-112">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="32851-113">해결 방법은 코드의 목적에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="32851-113">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="32851-114">이 MDA에서는 프로그램에 런타임에 바인딩된 시나리오가 있음을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="32851-114">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="32851-115">초기 바인딩 시나리오를 대체할 수 있는지 결정하거나 런타임에 바인딩된 시나리오의 성능을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-115">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="32851-116">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="32851-116">Effect on the Runtime</span></span>  

 <span data-ttu-id="32851-117">이 MDA는 생성된 모든 <xref:System.Reflection.MemberInfo> 캐시에 사용되도록 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="32851-117">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="32851-118">성능에 주는 영향은 매우 적습니다.</span><span class="sxs-lookup"><span data-stu-id="32851-118">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="32851-119">출력</span><span class="sxs-lookup"><span data-stu-id="32851-119">Output</span></span>  

 <span data-ttu-id="32851-120">MDA에서 <xref:System.Reflection.MemberInfo> 캐시가 생성되었음을 표시하는 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="32851-120">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="32851-121">디버거를 사용하여 프로그램에서 리플렉션을 사용하는 위치를 보여 주는 스택 추적을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32851-121">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="32851-122">구성</span><span class="sxs-lookup"><span data-stu-id="32851-122">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="32851-123">예제</span><span class="sxs-lookup"><span data-stu-id="32851-123">Example</span></span>  

 <span data-ttu-id="32851-124">이 샘플 코드에서는 `memberInfoCacheCreation` MDA를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="32851-124">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32851-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32851-125">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="32851-126">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="32851-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
