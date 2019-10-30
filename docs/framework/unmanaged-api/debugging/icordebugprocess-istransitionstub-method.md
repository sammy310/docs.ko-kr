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
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139392"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="2dffe-102">ICorDebugProcess::IsTransitionStub 메서드</span><span class="sxs-lookup"><span data-stu-id="2dffe-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="2dffe-103">관리 코드로의 전환을 발생 시킬 스텁 내에 주소가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dffe-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dffe-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dffe-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dffe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dffe-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2dffe-106">진행 해당 주소를 지정 하는 `CORDB_ADDRESS` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2dffe-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="2dffe-107">제한이 지정 된 주소가 관리 코드로의 전환을 발생 시키는 스텁 안에 있는 경우 `true` 되는 부울 값에 대 한 포인터입니다. 그렇지 않으면 \*`pbTransitionStub` `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dffe-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dffe-108">주의</span><span class="sxs-lookup"><span data-stu-id="2dffe-108">Remarks</span></span>  
 <span data-ttu-id="2dffe-109">`IsTransitionStub` 메서드는 관리 되지 않는 단계별 코드에서 관리 되는 스텝 퍼에 대 한 단계별 제어를 반환할 시기를 결정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dffe-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="2dffe-110">PE (이식 가능한 실행 파일) 파일의 정보를 살펴보면 전환 스텁을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dffe-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dffe-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dffe-111">Requirements</span></span>  
 <span data-ttu-id="2dffe-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dffe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dffe-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dffe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dffe-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dffe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dffe-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dffe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
