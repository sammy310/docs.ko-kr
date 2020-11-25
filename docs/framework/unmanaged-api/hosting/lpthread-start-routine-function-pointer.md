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
ms.openlocfilehash: c86b65e136869603f93253678108b2ffa9d388e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730073"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="e8a4d-102">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="e8a4d-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="e8a4d-103">스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e8a4d-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="e8a4d-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8a4d-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a4d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8a4d-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8a4d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8a4d-106">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="e8a4d-107">진행 실행을 시작한 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8a4d-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8a4d-108">설명</span><span class="sxs-lookup"><span data-stu-id="e8a4d-108">Remarks</span></span>  

 <span data-ttu-id="e8a4d-109">`LPTHREAD_START_ROUTINE`요소가 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e8a4d-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a4d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8a4d-110">Requirements</span></span>  

 <span data-ttu-id="e8a4d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8a4d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a4d-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e8a4d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8a4d-113">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e8a4d-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e8a4d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a4d-115">참조</span><span class="sxs-lookup"><span data-stu-id="e8a4d-115">See also</span></span>

- [<span data-ttu-id="e8a4d-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="e8a4d-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
