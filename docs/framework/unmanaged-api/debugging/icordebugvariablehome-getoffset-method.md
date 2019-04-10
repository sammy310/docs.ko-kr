---
title: ICorDebugVariableHome::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864cb893511bceabd61ce0064065b3866ce01dfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212598"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="c6631-102">ICorDebugVariableHome::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="c6631-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="c6631-103">변수에 대 한 기본 등록에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6631-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6631-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6631-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6631-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6631-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="c6631-106">[out] 기본 등록에서 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="c6631-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6631-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6631-107">Return Value</span></span>  
 <span data-ttu-id="c6631-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6631-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="c6631-109">값</span><span class="sxs-lookup"><span data-stu-id="c6631-109">Value</span></span>|<span data-ttu-id="c6631-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6631-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="c6631-111">변수가 레지스터 상대 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6631-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="c6631-112">변수를 레지스터 상대 메모리 위치에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6631-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6631-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6631-113">Requirements</span></span>  
 <span data-ttu-id="c6631-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6631-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6631-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6631-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6631-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6631-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6631-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c6631-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6631-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6631-118">See also</span></span>

- [<span data-ttu-id="c6631-119">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6631-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
