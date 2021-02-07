---
description: '자세히 알아보기: WAITORAND CALLBACK 함수 포인터'
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
ms.openlocfilehash: 6fd9e7eab56e48086eefcb26fc48cbf5f45d4a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679058"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="2e7f3-103">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="2e7f3-103">WAITORTIMERCALLBACK Function Pointer</span></span>

<span data-ttu-id="2e7f3-104">는 대기 핸들 ( <xref:System.Threading.WaitHandle> )이 신호를 받았거나 시간이 초과 되었음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-104">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="2e7f3-105">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e7f3-106">구문</span><span class="sxs-lookup"><span data-stu-id="2e7f3-106">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e7f3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e7f3-107">Parameters</span></span>  

 `lpParameter`  
 <span data-ttu-id="2e7f3-108">진행 호스트에서 정의한 정보를 포함 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-108">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="2e7f3-109">[in] `true` 대기 핸들 시간이 초과 되었거나 `false` 신호를 받은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-109">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e7f3-110">설명</span><span class="sxs-lookup"><span data-stu-id="2e7f3-110">Remarks</span></span>  

 <span data-ttu-id="2e7f3-111">`WAITORTIMERCALLBACK`요소가 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-111">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e7f3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e7f3-112">Requirements</span></span>  

 <span data-ttu-id="2e7f3-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e7f3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e7f3-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e7f3-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e7f3-115">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2e7f3-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2e7f3-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e7f3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7f3-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e7f3-117">See also</span></span>

- [<span data-ttu-id="2e7f3-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2e7f3-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
