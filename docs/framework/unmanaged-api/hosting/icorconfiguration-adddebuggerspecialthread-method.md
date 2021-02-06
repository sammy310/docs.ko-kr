---
description: '자세히 알아보기: ICorConfiguration:: AddDebuggerSpecialThread 메서드'
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
ms.openlocfilehash: b6904c2e4d5c265244ac096e0d64c2fc7f5d1be5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636717"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="93829-103">ICorConfiguration::AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="93829-103">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>

<span data-ttu-id="93829-104">관리 되거나 관리 되지 않는 디버깅 시나리오에서 디버거가 응용 프로그램을 중지 하는 동안 특정 스레드가 계속 실행 되도록 허용 해야 하는 디버깅 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93829-104">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93829-105">구문</span><span class="sxs-lookup"><span data-stu-id="93829-105">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93829-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93829-106">Parameters</span></span>  

 `dwSpecialThreadId`  
 <span data-ttu-id="93829-107">진행 계속 실행 되도록 허용 해야 하는 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="93829-107">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93829-108">설명</span><span class="sxs-lookup"><span data-stu-id="93829-108">Remarks</span></span>  

 <span data-ttu-id="93829-109">지정 된 스레드는 관리 코드를 실행 하거나 다른 방식으로 런타임을 입력할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93829-109">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="93829-110">이러한 스레드의 예는 레거시 스크립트 디버거를 지 원하는 in-process 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="93829-110">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93829-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93829-111">Requirements</span></span>  

 <span data-ttu-id="93829-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93829-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93829-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="93829-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93829-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93829-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93829-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93829-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93829-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93829-116">See also</span></span>

- [<span data-ttu-id="93829-117">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93829-117">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
