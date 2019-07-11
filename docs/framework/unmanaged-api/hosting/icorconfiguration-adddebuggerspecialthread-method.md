---
title: ICorConfiguration::AddDebuggerSpecialThread 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779900"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="aabe6-102">ICorConfiguration::AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="aabe6-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="aabe6-103">디버깅 서비스에 특정 스레드를 계속 디버거가 응용 프로그램을 중지 하는 동안 관리 되거나 관리 되지 않는 디버깅 시나리오는 동시 실행 수 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aabe6-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabe6-104">구문</span><span class="sxs-lookup"><span data-stu-id="aabe6-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aabe6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aabe6-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="aabe6-106">[in] 계속 실행 되도록 허용 되어야 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="aabe6-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aabe6-107">설명</span><span class="sxs-lookup"><span data-stu-id="aabe6-107">Remarks</span></span>  
 <span data-ttu-id="aabe6-108">지정된 된 스레드에 관리 되는 코드를 실행 하거나 런타임에 어떤 방식으로든에서 입력 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aabe6-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="aabe6-109">이러한 스레드의 예로 레거시 스크립트 디버거를 지원 하기 위해 프로세스에서 스레드를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aabe6-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aabe6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aabe6-110">Requirements</span></span>  
 <span data-ttu-id="aabe6-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aabe6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aabe6-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aabe6-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aabe6-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="aabe6-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aabe6-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aabe6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabe6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="aabe6-115">See also</span></span>

- [<span data-ttu-id="aabe6-116">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aabe6-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
