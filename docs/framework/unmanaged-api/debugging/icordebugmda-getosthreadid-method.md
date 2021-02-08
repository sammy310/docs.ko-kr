---
description: '자세히 알아보기: ICorDebugMDA:: GetOSThreadId 메서드'
title: ICorDebugMDA::GetOSThreadId 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: f965585a6e6060a14f0cbc2a80b46124b2751e0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801152"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="87d28-103">ICorDebugMDA::GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="87d28-103">ICorDebugMDA::GetOSThreadId Method</span></span>

<span data-ttu-id="87d28-104">[ICorDebugMDA](icordebugmda-interface.md) 가 나타내는 MDA (관리 디버깅 도우미)가 실행 중인 os (운영 체제) 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87d28-104">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d28-105">구문</span><span class="sxs-lookup"><span data-stu-id="87d28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87d28-106">Parameters</span></span>  

 `pOsTid`  
 <span data-ttu-id="87d28-107">제한이 OS 스레드 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87d28-107">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87d28-108">설명</span><span class="sxs-lookup"><span data-stu-id="87d28-108">Remarks</span></span>  

 <span data-ttu-id="87d28-109">ICorDebugThread 대신 OS 스레드를 사용 하 여 네이티브 스레드나 관리 코드를 아직 입력 하지 않은 관리 되는 스레드에서 MDA가 발생 하는 상황을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87d28-109">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d28-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87d28-110">Requirements</span></span>  

 <span data-ttu-id="87d28-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87d28-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d28-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87d28-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87d28-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87d28-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87d28-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d28-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d28-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87d28-115">See also</span></span>

- [<span data-ttu-id="87d28-116">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d28-116">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="87d28-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="87d28-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
