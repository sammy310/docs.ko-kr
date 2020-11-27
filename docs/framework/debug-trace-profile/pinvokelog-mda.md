---
title: pInvokeLog MDA
description: .NET에서 실행 하는 동안 사용 되는 각각의 고유한 플랫폼 호출 서명에 대해 활성화 된 MDA (pInvokeLog 관리 디버깅 도우미)를 이해 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: b8cb4805663a2b28a133f98503730199af695c4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271462"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="17916-103">pInvokeLog MDA</span><span class="sxs-lookup"><span data-stu-id="17916-103">pInvokeLog MDA</span></span>

<span data-ttu-id="17916-104">`pInvokeLog` MDA(관리 디버깅 도우미)는 실행 중에 사용되는 고유한 각 플랫폼 호출을 위해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="17916-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="17916-105">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="17916-105">Effect on the Runtime</span></span>  

 <span data-ttu-id="17916-106">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17916-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="17916-107">출력</span><span class="sxs-lookup"><span data-stu-id="17916-107">Output</span></span>  

 <span data-ttu-id="17916-108">실행 중에 사용된 플랫폼 호출 시그니처를 나타내는 메시지.</span><span class="sxs-lookup"><span data-stu-id="17916-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="17916-109">구성</span><span class="sxs-lookup"><span data-stu-id="17916-109">Configuration</span></span>  

 <span data-ttu-id="17916-110">일치하는 각 요소는 플랫폼 호출을 수행하는 .dll 파일을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="17916-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17916-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17916-111">See also</span></span>

- [<span data-ttu-id="17916-112">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="17916-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="17916-113">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="17916-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
