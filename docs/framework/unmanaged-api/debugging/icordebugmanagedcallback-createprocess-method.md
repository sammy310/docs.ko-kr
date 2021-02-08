---
description: '자세히 알아보기: ICorDebugManagedCallback:: CreateProcess 메서드'
title: ICorDebugManagedCallback::CreateProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: 564c9862dd90431f0626204fdfe49e59b85a124d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791051"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="78e06-103">ICorDebugManagedCallback::CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="78e06-103">ICorDebugManagedCallback::CreateProcess Method</span></span>

<span data-ttu-id="78e06-104">프로세스가 처음으로 연결 되거나 시작 된 경우 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="78e06-104">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78e06-105">구문</span><span class="sxs-lookup"><span data-stu-id="78e06-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78e06-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78e06-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="78e06-107">진행 연결 되거나 시작 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78e06-107">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78e06-108">설명</span><span class="sxs-lookup"><span data-stu-id="78e06-108">Remarks</span></span>  

 <span data-ttu-id="78e06-109">이 메서드는 공용 언어 런타임이 초기화 될 때까지 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78e06-109">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="78e06-110">대부분의 [ICorDebug](icordebug-interface.md) 메서드는 콜백 전에 CORDBG_E_NOTREADY을 반환 합니다 `CreateProcess` .</span><span class="sxs-lookup"><span data-stu-id="78e06-110">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78e06-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78e06-111">Requirements</span></span>  

 <span data-ttu-id="78e06-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78e06-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78e06-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78e06-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78e06-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78e06-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78e06-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78e06-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e06-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78e06-116">See also</span></span>

- [<span data-ttu-id="78e06-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78e06-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
