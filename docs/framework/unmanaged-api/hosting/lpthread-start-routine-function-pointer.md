---
description: '자세한 정보: 함수 포인터 LPTHREAD_START_ROUTINE'
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
ms.openlocfilehash: 9f79cffb0b5290031915b453353dd47cb3959970
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679812"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="67f17-103">LPTHREAD_START_ROUTINE 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="67f17-103">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="67f17-104">스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="67f17-104">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="67f17-105">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67f17-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f17-106">구문</span><span class="sxs-lookup"><span data-stu-id="67f17-106">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f17-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67f17-107">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="67f17-108">진행 실행을 시작한 코드에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="67f17-108">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67f17-109">설명</span><span class="sxs-lookup"><span data-stu-id="67f17-109">Remarks</span></span>  

 <span data-ttu-id="67f17-110">`LPTHREAD_START_ROUTINE`요소가 콜백 함수 이며 호스팅 응용 프로그램의 작성기에서 구현 해야 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="67f17-110">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f17-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67f17-111">Requirements</span></span>  

 <span data-ttu-id="67f17-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67f17-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f17-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67f17-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67f17-114">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="67f17-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="67f17-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f17-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f17-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67f17-116">See also</span></span>

- [<span data-ttu-id="67f17-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="67f17-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
