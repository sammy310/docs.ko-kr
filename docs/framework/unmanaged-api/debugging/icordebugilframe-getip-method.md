---
title: ICorDebugILFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178833"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="08d74-102">ICorDebugILFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="08d74-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="08d74-103">명령 포인터의 값과 명령 포인터의 값을 가져오는 방법을 설명하는 비트 조합 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d74-104">구문</span><span class="sxs-lookup"><span data-stu-id="08d74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08d74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08d74-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="08d74-106">【아웃】 명령 포인터의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="08d74-107">【아웃】 명령 포인터의 값을 가져오는 방법을 설명하는 CorDebugMappingResult 열거 형 값의 비트 조합에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08d74-108">설명</span><span class="sxs-lookup"><span data-stu-id="08d74-108">Remarks</span></span>  
 <span data-ttu-id="08d74-109">명령 포인터의 값은 스택 프레임이 함수의 Microsoft 중간 언어(MSIL) 코드로 오프셋되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="08d74-110">스택 프레임이 활성 상태인 경우 이 주소는 실행할 다음 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="08d74-111">스택 프레임이 활성화되어 있지 않으면 이 주소는 스택 프레임이 다시 활성화될 때 실행하는 다음 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="08d74-112">이 프레임이 JIT(적시) 컴파일된 프레임인 경우 명령 포인터의 값은 실제 네이티브 명령 포인터에서 뒤로 매핑하여 결정되므로 값은 대략적인 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d74-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d74-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08d74-113">Requirements</span></span>  
 <span data-ttu-id="08d74-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08d74-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d74-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08d74-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08d74-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08d74-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08d74-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d74-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
