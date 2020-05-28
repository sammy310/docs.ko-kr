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
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009453"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="f9f17-102">WAITORTIMERCALLBACK 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="f9f17-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="f9f17-103">는 대기 핸들 ( <xref:System.Threading.WaitHandle> )이 신호를 받았거나 시간이 초과 되었음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f9f17-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="f9f17-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f17-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f17-105">구문</span><span class="sxs-lookup"><span data-stu-id="f9f17-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9f17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9f17-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="f9f17-107">진행 호스트에서 정의한 정보를 포함 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9f17-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="f9f17-108">[in] `true` 대기 핸들 시간이 초과 되었거나 `false` 신호를 받은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="f9f17-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f17-109">설명</span><span class="sxs-lookup"><span data-stu-id="f9f17-109">Remarks</span></span>  
 <span data-ttu-id="f9f17-110">`WAITORTIMERCALLBACK`요소가 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9f17-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9f17-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9f17-111">Requirements</span></span>  
 <span data-ttu-id="f9f17-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9f17-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9f17-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f9f17-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9f17-114">**라이브러리:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="f9f17-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f9f17-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9f17-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f17-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9f17-116">See also</span></span>

- [<span data-ttu-id="f9f17-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f9f17-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
