---
title: 'ICorDebugVariableHome:: GetOffset 메서드'
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
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396763"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="c00f2-102">ICorDebugVariableHome:: GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="c00f2-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="c00f2-103">변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c00f2-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c00f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c00f2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c00f2-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="c00f2-106">제한이 기본 레지스터의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="c00f2-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c00f2-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c00f2-107">Return Value</span></span>  
 <span data-ttu-id="c00f2-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c00f2-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="c00f2-109">값</span><span class="sxs-lookup"><span data-stu-id="c00f2-109">Value</span></span>|<span data-ttu-id="c00f2-110">Description</span><span class="sxs-lookup"><span data-stu-id="c00f2-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="c00f2-111">변수가 등록 관련 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c00f2-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="c00f2-112">변수가 등록 관련 메모리 위치에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c00f2-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c00f2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c00f2-113">Requirements</span></span>  
 <span data-ttu-id="c00f2-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c00f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00f2-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c00f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c00f2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c00f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c00f2-117">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00f2-118">참조</span><span class="sxs-lookup"><span data-stu-id="c00f2-118">See also</span></span>

- [<span data-ttu-id="c00f2-119">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c00f2-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
