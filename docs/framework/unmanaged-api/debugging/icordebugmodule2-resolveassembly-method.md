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
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210038"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="3e2e5-102">ICorDebugModule2::ResolveAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="3e2e5-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="3e2e5-103">지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e2e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e2e5-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="3e2e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e2e5-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="3e2e5-106">진행 `mdToken`어셈블리를 참조 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="3e2e5-107">제한이 어셈블리를 나타내는 ICorDebugAssembly 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e2e5-108">설명</span><span class="sxs-lookup"><span data-stu-id="3e2e5-108">Remarks</span></span>

<span data-ttu-id="3e2e5-109">가 호출 될 때 어셈블리가 아직 로드 되지 않은 경우에는 `ResolveAssembly` HRESULT 값이 CORDBG_E_CANNOT_RESOLVE_ASSEMBLY 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e2e5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e2e5-110">Requirements</span></span>

<span data-ttu-id="3e2e5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3e2e5-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e2e5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="3e2e5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e2e5-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3e2e5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e2e5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
