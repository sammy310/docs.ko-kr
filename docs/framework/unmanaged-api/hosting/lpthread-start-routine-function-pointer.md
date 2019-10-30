---
title: LPTHREAD_START_ROUTINE 함수 포인터
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090871"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="b5fb0-102">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="b5fb0-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="b5fb0-103">스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="b5fb0-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5fb0-105">구문</span><span class="sxs-lookup"><span data-stu-id="b5fb0-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5fb0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5fb0-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="b5fb0-107">진행 실행을 시작한 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5fb0-108">주의</span><span class="sxs-lookup"><span data-stu-id="b5fb0-108">Remarks</span></span>  
 <span data-ttu-id="b5fb0-109">`LPTHREAD_START_ROUTINE` 점이 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5fb0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5fb0-110">Requirements</span></span>  
 <span data-ttu-id="b5fb0-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5fb0-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b5fb0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5fb0-113">**라이브러리:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="b5fb0-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b5fb0-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5fb0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5fb0-115">참조</span><span class="sxs-lookup"><span data-stu-id="b5fb0-115">See also</span></span>

- [<span data-ttu-id="b5fb0-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="b5fb0-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
