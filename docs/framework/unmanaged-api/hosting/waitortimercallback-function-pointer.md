---
title: WAITORTIMERCALLBACK 함수 포인터
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8cf12fc6828c5e439a6a86532f22b8a598a9f03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120993"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="22ce8-102">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="22ce8-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="22ce8-103">호스트는 대기 핸들에 알리는 함수를 가리키는 (<xref:System.Threading.WaitHandle>) 하거나 신호가 전달 되거나 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="22ce8-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="22ce8-104">이 함수 포인터에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="22ce8-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ce8-105">구문</span><span class="sxs-lookup"><span data-stu-id="22ce8-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ce8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22ce8-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="22ce8-107">[in] 호스트에 의해 정의 된 정보를 포함 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="22ce8-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="22ce8-108">[in] `true` 대기 핸들을 초과 하는 경우 또는 `false` 된 신호를 받은 경우.</span><span class="sxs-lookup"><span data-stu-id="22ce8-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22ce8-109">설명</span><span class="sxs-lookup"><span data-stu-id="22ce8-109">Remarks</span></span>  
 <span data-ttu-id="22ce8-110">함수는 `WAITORTIMERCALLBACK` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성기에 의해 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ce8-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ce8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22ce8-111">Requirements</span></span>  
 <span data-ttu-id="22ce8-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22ce8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ce8-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22ce8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22ce8-114">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="22ce8-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="22ce8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ce8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ce8-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="22ce8-116">See also</span></span>

- [<span data-ttu-id="22ce8-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="22ce8-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
