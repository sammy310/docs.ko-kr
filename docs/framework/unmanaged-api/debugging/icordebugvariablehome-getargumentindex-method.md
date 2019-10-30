---
title: 'ICorDebugVariableHome:: GetArgumentIndex 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 86b2815c6f95c674c49bba7455e8497192bd8bac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125148"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="5b8e7-102">ICorDebugVariableHome:: GetArgumentIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="5b8e7-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="5b8e7-103">함수 인수의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b8e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b8e7-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="5b8e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b8e7-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="5b8e7-106">제한이 인수 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="5b8e7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5b8e7-107">Return Value</span></span>

<span data-ttu-id="5b8e7-108">메서드는 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-108">The method returns the following values.</span></span>

|<span data-ttu-id="5b8e7-109">값</span><span class="sxs-lookup"><span data-stu-id="5b8e7-109">Value</span></span>|<span data-ttu-id="5b8e7-110">설명</span><span class="sxs-lookup"><span data-stu-id="5b8e7-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="5b8e7-111">메서드 호출에서 유효한 인수 인덱스를 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="5b8e7-112">현재 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) 인스턴스는 지역 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5b8e7-113">주의</span><span class="sxs-lookup"><span data-stu-id="5b8e7-113">Remarks</span></span>

<span data-ttu-id="5b8e7-114">인수 인덱스는이 인수에 대 한 메타 데이터를 검색 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b8e7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b8e7-115">Requirements</span></span>

<span data-ttu-id="5b8e7-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b8e7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5b8e7-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b8e7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="5b8e7-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b8e7-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5b8e7-119">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b8e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5b8e7-120">참조</span><span class="sxs-lookup"><span data-stu-id="5b8e7-120">See also</span></span>

- [<span data-ttu-id="5b8e7-121">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b8e7-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
