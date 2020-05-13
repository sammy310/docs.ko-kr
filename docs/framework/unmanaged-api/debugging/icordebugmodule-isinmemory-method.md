---
title: ICorDebugModule::IsInMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: c5fa55a84ed8907a5072f6099c3bf02cd6d78683
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213130"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="f0f9e-102">ICorDebugModule::IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="f0f9e-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="f0f9e-103">이 모듈이 메모리에만 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9e-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0f9e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f9e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0f9e-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="f0f9e-106">[out] `true` 이 모듈은 메모리에만 존재 합니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9e-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f9e-107">설명</span><span class="sxs-lookup"><span data-stu-id="f0f9e-107">Remarks</span></span>  
 <span data-ttu-id="f0f9e-108">CLR (공용 언어 런타임)은 원시 바이트 스트림에서 모듈 로드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9e-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="f0f9e-109">이러한 모듈은 *메모리 내 모듈* 이라고 하며 디스크에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f9e-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f9e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0f9e-110">Requirements</span></span>  
 <span data-ttu-id="f0f9e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0f9e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f9e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0f9e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0f9e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0f9e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0f9e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f9e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f9e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0f9e-115">See also</span></span>
