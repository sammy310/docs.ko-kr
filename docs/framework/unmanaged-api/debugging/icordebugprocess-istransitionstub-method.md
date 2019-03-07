---
title: ICorDebugProcess::IsTransitionStub 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488190"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="d5d35-102">ICorDebugProcess::IsTransitionStub 메서드</span><span class="sxs-lookup"><span data-stu-id="d5d35-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="d5d35-103">관리 코드로 전환 하는 스텁을 내부 주소 인지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5d35-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d35-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5d35-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5d35-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5d35-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d5d35-106">[in] `CORDB_ADDRESS` 해당 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d35-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="d5d35-107">[out] 부울 값에 대 한 포인터 `true` 관리 되는 코드를 전환 하는 스텁을 내에서 지정된 된 주소 이면 그렇지 않은 경우 \*`pbTransitionStub` 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d35-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5d35-108">설명</span><span class="sxs-lookup"><span data-stu-id="d5d35-108">Remarks</span></span>  
 <span data-ttu-id="d5d35-109">`IsTransitionStub` 메서드 수 단계별 비관리 코드에서 관리 스텝 퍼에 단계별 실행 제어를 반환 하는 시기를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d35-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="d5d35-110">이식 가능한 실행 파일 (PE) 파일에서 정보를 확인 하 여 전환 스텁을 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d35-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d35-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5d35-111">Requirements</span></span>  
 <span data-ttu-id="d5d35-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5d35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d35-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5d35-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5d35-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5d35-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5d35-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d35-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
