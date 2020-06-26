---
title: dllMainReturnsFalse MDA
description: .NET의 dllMainReturnsFalse 관리 디버깅 도우미에 대해 읽어 보세요. DLL 초기화에 실패 한 경우이 MDA가 활성화 됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 21d5e37d6823876e07cf5b2cbb881c1cf8b47b11
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416059"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="f0beb-104">dllMainReturnsFalse MDA</span><span class="sxs-lookup"><span data-stu-id="f0beb-104">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="f0beb-105">DLL_PROCESS_ATTACH로 인해 호출된 사용자 어셈블리의 관리되는 `DllMain` 함수가 FALSE를 반환하면 `dllMainReturnsFalse` MDA(관리 디버깅 도우미)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-105">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f0beb-106">증상</span><span class="sxs-lookup"><span data-stu-id="f0beb-106">Symptoms</span></span>  
 <span data-ttu-id="f0beb-107">`DllMain` 함수가 FALSE를 반환했고 이는 함수가 제대로 실행되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-107">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="f0beb-108">`DllMain` 함수에는 일반적으로 중요한 초기화 코드가 포함되므로 이로 인해 결정되지 않은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-108">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f0beb-109">원인</span><span class="sxs-lookup"><span data-stu-id="f0beb-109">Cause</span></span>  
 <span data-ttu-id="f0beb-110">로드 시 DLL 초기화에 대한 DLL_PROCESS_ATTACH로 인해 `DllMain` 함수가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-110">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="f0beb-111">함수가 FALSE를 반환하면 DLL 초기화가 실패했음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-111">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f0beb-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f0beb-112">Resolution</span></span>  
 <span data-ttu-id="f0beb-113">실패한 DLL의 `DllMain` 함수 코드를 분석하고 초기화 실패의 원인을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-113">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f0beb-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f0beb-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="f0beb-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="f0beb-116">`DllMain`의 반환 값에 대한 데이터만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-116">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f0beb-117">출력</span><span class="sxs-lookup"><span data-stu-id="f0beb-117">Output</span></span>  
 <span data-ttu-id="f0beb-118">DLL_PROCESS_ATTACH로 인해 호출되는 `DllMain` 함수가 FALSE를 반환했음을 나타내는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-118">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="f0beb-119">이 MDA는 `DllMain`이 관리 코드에서 구현된 경우에만 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0beb-119">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f0beb-120">구성</span><span class="sxs-lookup"><span data-stu-id="f0beb-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0beb-121">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f0beb-121">See also</span></span>

- [<span data-ttu-id="f0beb-122">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f0beb-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
