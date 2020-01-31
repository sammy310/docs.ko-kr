---
title: 'ICorDebugType2:: GetTypeID 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791236"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="cc9bf-102">ICorDebugType2:: GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="cc9bf-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="cc9bf-103">이 형식에 대 한 [COR_TYPEID](cor-typeid-structure.md) 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc9bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc9bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc9bf-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="cc9bf-106">제한이 이 ICorDebugType에 대 한 [COR_TYPEID](cor-typeid-structure.md) 에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc9bf-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cc9bf-107">Return Value</span></span>  
 <span data-ttu-id="cc9bf-108">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="cc9bf-109">`HRESULT` 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="cc9bf-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="cc9bf-110">Return code</span></span>|<span data-ttu-id="cc9bf-111">설명</span><span class="sxs-lookup"><span data-stu-id="cc9bf-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="cc9bf-112">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-112">Method succeeded.</span></span> <span data-ttu-id="cc9bf-113">메서드가 올바른 [COR_TYPEID](cor-typeid-structure.md)를 검색 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="cc9bf-114">형식이 로드 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="cc9bf-115">유형이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc9bf-116">주의</span><span class="sxs-lookup"><span data-stu-id="cc9bf-116">Remarks</span></span>  
 <span data-ttu-id="cc9bf-117">이 메서드는 런타임에 로드 될 수 있거나 런타임에 로드 된 형식을 식별 하는 불투명 핸들 역할을 하는 [COR_TYPEID](cor-typeid-structure.md)에 대해 런타임에 로드 될 수 있는 형식을 나타내는 ICorDebugType의 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="cc9bf-118">ICorDebugType가 나타내는 형식이 아직 로드 되지 않은 경우이 메서드는 `CORDBG_E_CLASS_NOT_LOADED`반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="cc9bf-119">형식이 지원 되지 않는 경우 `CORDBG_E_UNSUPPORTED`반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc9bf-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc9bf-120">Requirements</span></span>  
 <span data-ttu-id="cc9bf-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc9bf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc9bf-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc9bf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc9bf-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc9bf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc9bf-124">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc9bf-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9bf-125">참조</span><span class="sxs-lookup"><span data-stu-id="cc9bf-125">See also</span></span>

- [<span data-ttu-id="cc9bf-126">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc9bf-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)
