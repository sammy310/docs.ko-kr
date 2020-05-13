---
title: ICorDebugProcess5::EnableNGENPolicy 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: fa3cbfee0359b8477f9efe88fe72837b86611bf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212804"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="46b4a-102">ICorDebugProcess5::EnableNGENPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="46b4a-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="46b4a-103">응용 프로그램에서 관리 되는 디버거를 실행 하는 동안 네이티브 이미지를 로드 하는 방법을 결정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b4a-104">구문</span><span class="sxs-lookup"><span data-stu-id="46b4a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b4a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46b4a-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="46b4a-106">진행 응용 프로그램이 관리 되는 디버거에서 실행 되는 동안 네이티브 이미지를 로드 하는 방법을 결정 하는 [Cordebugngenpolicy](cordebugngenpolicy-enumeration.md) 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b4a-107">설명</span><span class="sxs-lookup"><span data-stu-id="46b4a-107">Remarks</span></span>  
 <span data-ttu-id="46b4a-108">정책이 성공적으로 설정 되 면이 메서드는를 반환 `S_OK` 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="46b4a-109">`ePolicy`가 [Cordebugngenpolicy](cordebugngenpolicy-enumeration.md)에서 정의한 열거형 값의 범위를 벗어나면 메서드가 반환 되 `E_INVALIDARG` 고 메서드 호출이 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="46b4a-110">네이티브 이미지 생성기 (Ngen.exe)의 정책을 업데이트할 수 없는 경우이 메서드는를 반환 `E_FAIL` 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="46b4a-111">`ICorDebugProcess5::EnableNGenPolicy`프로세스 수명 중에 언제 든 지 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="46b4a-112">정책은 정책이 설정 된 후에 로드 되는 모든 모듈에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b4a-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b4a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46b4a-113">Requirements</span></span>  
 <span data-ttu-id="46b4a-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46b4a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b4a-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46b4a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46b4a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46b4a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46b4a-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b4a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46b4a-118">See also</span></span>

- [<span data-ttu-id="46b4a-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46b4a-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="46b4a-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46b4a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="46b4a-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="46b4a-121">Debugging</span></span>](index.md)
