---
title: ICorDebugModule2::ResolveAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359694"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="839dd-102">ICorDebugModule2::ResolveAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="839dd-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="839dd-103">지정 된 메타 데이터 토큰이 참조 되는 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="839dd-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="839dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="839dd-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="839dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="839dd-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="839dd-106">[in] `mdToken` 어셈블리를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="839dd-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="839dd-107">[out] 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="839dd-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="839dd-108">설명</span><span class="sxs-lookup"><span data-stu-id="839dd-108">Remarks</span></span>

<span data-ttu-id="839dd-109">어셈블리는 로드 되지 않았으면 때 `ResolveAssembly` 호출 되는 HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="839dd-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="839dd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="839dd-110">Requirements</span></span>

<span data-ttu-id="839dd-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="839dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="839dd-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="839dd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="839dd-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="839dd-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="839dd-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="839dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
